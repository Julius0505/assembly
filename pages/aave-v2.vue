<template>
  <div>
    <div>
      <nuxt-link
        to="/"
        class="text-[#C0C5D7] text-lg font-semibold flex items-center"
      >
        <BackIcon class="w-4 h-4 mr-3" />
        Apps
      </nuxt-link>
    </div>

    <div class="mt-10 flex items-center justify-between">
      <div class="flex items-center">
        <div
          style="background: radial-gradient(42.15% 42.15% at 48.94% 48.94%, #D6DAE0 75.67%, #F0F3F9 100%), #C4C4C4;"
          class="w-16 h-16 rounded-full flex items-center justify-center border border-[#CCDCF3]"
        >
          <div
            class="w-12 h-12 rounded-full flex items-center justify-center bg-[#1874FF]"
          >
            <AaveIcon class="w-8 h-8 text-white" />
          </div>
        </div>
        <h1 class="ml-4 text-primary-black text-2xl font-semibold">Aave v2</h1>
      </div>

      <ButtonCTAOutlined
        class="px-4 h-9 w-[173px]"
        @click="$router.push({ hash: 'strategies?protocol=aaveV2' })"
      >
        Strategies

        <svg
          class="ml-auto"
          width="11"
          height="10"
          viewBox="0 0 11 10"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M4.3815 8.76139C4.38149 8.99703 4.64068 9.1407 4.8405 9.01581L10.859 5.25425C11.047 5.13675 11.047 4.86295 10.859 4.74545L4.84088 0.984069C4.64108 0.859187 4.38189 1.00283 4.38188 1.23845L4.38179 2.97869C4.38178 3.14437 4.24747 3.27867 4.08179 3.27867L1.23894 3.27867C1.07325 3.27867 0.93894 3.41299 0.93894 3.57867L0.93894 6.42096C0.93894 6.58664 1.07325 6.72096 1.23894 6.72096L4.08159 6.72096C4.24728 6.72096 4.3816 6.85528 4.38159 7.02097L4.3815 8.76139Z"
            fill="#1874FF"
          />
        </svg>
      </ButtonCTAOutlined>
    </div>

    <div class="mt-10" v-if="position">
      <h2 class="text-primary-gray text-lg font-semibold">Overview</h2>

      <div
        class="px-1 mt-6 grid w-full grid-cols-1 gap-4 sm:grid-cols-3 xl:gap-[18px]"
      >
        <div class="shadow rounded-lg py-8 px-6 flex">
          <div class="flex-1">
            <h3 class="text-2xl text-primary-black font-medium">
              {{ formatUsd(totalSupply) }}
            </h3>
            <p class="mt-4 text-primary-gray font-medium">Lend</p>
          </div>
          <div class="flex items-center">
            <svg
              width="27"
              height="29"
              viewBox="0 0 27 29"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M1.34917 12C0.603705 12 -7.62939e-06 12.6037 -7.62939e-06 13.3492V26.8498C-7.62939e-06 27.5953 0.603705 28.199 1.34917 28.199H25.6496C26.395 28.199 27 27.5953 27 26.8498V13.3492C27 12.6037 26.395 12 25.6496 12H1.34917ZM3.93109 14.6996H23.0676C23.1684 14.9836 23.3312 15.2415 23.5442 15.4545C23.7573 15.6675 24.0152 15.8304 24.2991 15.9311V24.2679C24.0154 24.3688 23.7578 24.5317 23.5449 24.7447C23.3321 24.9577 23.1695 25.2156 23.0689 25.4994H3.93109C3.83052 25.2153 3.66775 24.9574 3.45469 24.7443C3.24163 24.5312 2.98365 24.3685 2.69961 24.2679V15.9311C2.98365 15.8305 3.24163 15.6678 3.45469 15.4547C3.66775 15.2416 3.83052 14.9837 3.93109 14.6996ZM13.4994 16.0501C12.4252 16.0501 11.3951 16.4768 10.6355 17.2363C9.876 17.9958 9.4493 19.026 9.4493 20.1001C9.4493 21.1743 9.876 22.2044 10.6355 22.964C11.3951 23.7235 12.4252 24.1502 13.4994 24.1502C14.5735 24.1502 15.6037 23.7235 16.3632 22.964C17.1227 22.2044 17.5494 21.1743 17.5494 20.1001C17.5494 19.026 17.1227 17.9958 16.3632 17.2363C15.6037 16.4768 14.5735 16.0501 13.4994 16.0501ZM6.74968 18.7497C6.39185 18.7497 6.04868 18.8918 5.79566 19.1448C5.54264 19.3979 5.4005 19.741 5.4005 20.0989C5.4005 20.4567 5.54264 20.7999 5.79566 21.0529C6.04868 21.3059 6.39185 21.448 6.74968 21.448C7.1075 21.448 7.45067 21.3059 7.70369 21.0529C7.95671 20.7999 8.09886 20.4567 8.09886 20.0989C8.09886 19.741 7.95671 19.3979 7.70369 19.1448C7.45067 18.8918 7.1075 18.7497 6.74968 18.7497ZM20.2491 18.7497C19.8911 18.7497 19.5477 18.8919 19.2946 19.145C19.0415 19.3982 18.8992 19.7415 18.8992 20.0995C18.8992 20.4575 19.0415 20.8008 19.2946 21.054C19.5477 21.3071 19.8911 21.4493 20.2491 21.4493C20.607 21.4493 20.9504 21.3071 21.2035 21.054C21.4566 20.8008 21.5989 20.4575 21.5989 20.0995C21.5989 19.7415 21.4566 19.3982 21.2035 19.145C20.9504 18.8919 20.607 18.7497 20.2491 18.7497Z"
                fill="#209B9F"
              />
              <path
                d="M9.26922 5.85639L12.8282 9.41665C12.9101 9.50186 13.0083 9.56957 13.1171 9.61569C13.2259 9.66181 13.3429 9.68538 13.461 9.68497C13.5793 9.68521 13.6963 9.66144 13.8051 9.61511C13.9139 9.56877 14.0121 9.50082 14.0939 9.41538L17.6529 5.85639C17.7382 5.77424 17.8061 5.67566 17.8524 5.5666C17.8986 5.45754 17.9224 5.34024 17.9221 5.22176C17.9219 5.10329 17.8977 4.98609 17.851 4.87721C17.8043 4.76833 17.736 4.67003 17.6503 4.58821C17.4829 4.42155 17.2575 4.32628 17.0213 4.32243C16.7834 4.32597 16.5564 4.42224 16.3885 4.59075L14.3634 6.61578V1.90125C14.3651 1.78233 14.343 1.66428 14.2982 1.55409C14.2534 1.44391 14.187 1.34383 14.1029 1.25979C14.0187 1.17575 13.9185 1.10946 13.8083 1.06486C13.698 1.02025 13.58 0.998235 13.461 1.00011C13.3422 0.998406 13.2243 1.02055 13.1142 1.06523C13.0041 1.10992 12.9041 1.17623 12.82 1.26025C12.736 1.34427 12.6697 1.44429 12.625 1.55439C12.5803 1.66449 12.5582 1.78244 12.5599 1.90125V6.61704L10.5349 4.59201C10.3672 4.42305 10.1401 4.3263 9.90204 4.32243C9.66419 4.32597 9.43713 4.42224 9.26922 4.59075C9.18408 4.67269 9.11636 4.77098 9.0701 4.87971C9.02384 4.98845 9 5.1054 9 5.22357C9 5.34173 9.02384 5.45869 9.0701 5.56742C9.11636 5.67616 9.18408 5.77444 9.26922 5.85639Z"
                fill="#209B9F"
                stroke="#209B9F"
                stroke-width="0.3"
              />
            </svg>
          </div>
        </div>

        <div class="shadow rounded-lg py-8 px-6 flex">
          <div class="flex-1">
            <h3 class="text-2xl text-primary-black font-medium">
              {{ formatUsd(totalBorrow) }}
            </h3>
            <p class="mt-4 text-primary-gray font-medium">Borrowed</p>
          </div>
          <div class="flex items-center">
            <svg
              width="27"
              height="28"
              viewBox="0 0 27 28"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M1.34511 11C0.601893 11 0 11.6019 0 12.3451V25.8051C0 26.5483 0.601893 27.1502 1.34511 27.1502H25.5722C26.3155 27.1502 26.9186 26.5483 26.9186 25.8051V12.3451C26.9186 11.6019 26.3155 11 25.5722 11H1.34511ZM3.91924 13.6915H22.9981C23.0985 13.9746 23.2609 14.2317 23.4733 14.4441C23.6857 14.6565 23.9428 14.8188 24.2259 14.9192V23.2309C23.943 23.3315 23.6861 23.4939 23.474 23.7063C23.2618 23.9187 23.0997 24.1757 22.9994 24.4587H3.91924C3.81898 24.1755 3.6567 23.9183 3.44428 23.7059C3.23186 23.4935 2.97466 23.3312 2.69148 23.2309V14.9192C2.97466 14.819 3.23186 14.6567 3.44428 14.4443C3.6567 14.2319 3.81898 13.9747 3.91924 13.6915ZM13.4587 15.0379C12.3878 15.0379 11.3607 15.4633 10.6035 16.2205C9.84624 16.9778 9.42082 18.0048 9.42082 19.0757C9.42082 20.1466 9.84624 21.1737 10.6035 21.9309C11.3607 22.6882 12.3878 23.1136 13.4587 23.1136C14.5296 23.1136 15.5566 22.6882 16.3139 21.9309C17.0711 21.1737 17.4965 20.1466 17.4965 19.0757C17.4965 18.0048 17.0711 16.9778 16.3139 16.2205C15.5566 15.4633 14.5296 15.0379 13.4587 15.0379ZM6.72934 17.7293C6.37259 17.7293 6.03046 17.8711 5.7782 18.1233C5.52594 18.3756 5.38423 18.7177 5.38423 19.0744C5.38423 19.4312 5.52594 19.7733 5.7782 20.0256C6.03046 20.2778 6.37259 20.4196 6.72934 20.4196C7.08608 20.4196 7.42822 20.2778 7.68048 20.0256C7.93273 19.7733 8.07445 19.4312 8.07445 19.0744C8.07445 18.7177 7.93273 18.3756 7.68048 18.1233C7.42822 17.8711 7.08608 17.7293 6.72934 17.7293ZM20.188 17.7293C19.8311 17.7293 19.4888 17.8711 19.2364 18.1235C18.9841 18.3759 18.8423 18.7182 18.8423 19.0751C18.8423 19.432 18.9841 19.7743 19.2364 20.0267C19.4888 20.279 19.8311 20.4208 20.188 20.4208C20.5449 20.4208 20.8872 20.279 21.1396 20.0267C21.392 19.7743 21.5338 19.432 21.5338 19.0751C21.5338 18.7182 21.392 18.3759 21.1396 18.1235C20.8872 17.8711 20.5449 17.7293 20.188 17.7293Z"
                fill="#CA8700"
              />
              <path
                d="M17.5573 3.7854H10.6173C10.0946 3.7854 9.6709 4.20911 9.6709 4.73177C9.6709 5.25444 10.0946 5.67815 10.6173 5.67815H17.5573C18.08 5.67815 18.5037 5.25444 18.5037 4.73177C18.5037 4.20911 18.08 3.7854 17.5573 3.7854Z"
                fill="#CA8700"
              />
              <path
                d="M17.5573 0H10.6173C10.0946 0 9.6709 0.423705 9.6709 0.946372C9.6709 1.46904 10.0946 1.89274 10.6173 1.89274H17.5573C18.08 1.89274 18.5037 1.46904 18.5037 0.946372C18.5037 0.423705 18.08 0 17.5573 0Z"
                fill="#CA8700"
              />
            </svg>
          </div>
        </div>

        <div class="shadow rounded-lg py-8 px-6 flex">
          <div class="flex-1">
            <div class="flex justify-between items-center">
              <h3 class="text-2xl text-primary-black font-medium">
                {{ formatPercent(status) }}
              </h3>
              <Badge class="w-18 xxl:w-23" :color="color">{{ text }}</Badge>
            </div>
            <div
              class="mt-4 flex justify-between items-center text-primary-gray font-medium"
            >
              <div class="flex items-center whitespace-no-wrap">
                <div>D/C (%)</div>

                <div class="ml-2"><Info text="Debt/Collateral ratio" /></div>
              </div>
              <span>Max - {{ formatPercent(maxLiquidation) }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-[60px]">
      <div
        class="w-full flex flex-col mt-6 sm:flex-row sm:items-center sm:justify-between xl:mt-4"
      >
        <h2 class="text-primary-gray text-lg font-semibold">Your Positions</h2>

        <div class="mt-4 sm:mt-0 sm:mr-1">
          <SearchInput
            v-model.trim="search"
            dense
            class="w-[200px]"
            placeholder="Search positions"
          />
        </div>
      </div>
      <div
        class="mt-3 grid w-full grid-cols-1 gap-4 sm:grid-cols-2 xxl:gap-6 min-w-max-content px-1"
      >
        <div v-for="item in filteredPositions" :key="item.key">
          <card-aave
            :token-key="item.key"
            :supply="item.supply"
            :supply-usd="item.supplyUsd"
            :supply-rate="item.supplyRate"
            :borrow="item.borrow"
            :borrow-usd="item.borrowUsd"
            :borrow-rate="item.borrowRate"
            :type="item.type"
            :supply-reward-rate="item.supplyRewardRate"
            :borrow-reward-rate="item.borrowRewardRate"
            reward-token-name="MATIC"
            reward-currency="matic"
            :cf="item.cf"
            :ll="item.ll"
            :borrow-enabled="item.borrowEnabled"
            :price-in-usd="item.priceInUsd"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed } from "@nuxtjs/composition-api";
import BackIcon from "~/assets/icons/back.svg?inline";
import { useAaveV2Position } from "~/composables/protocols/useAaveV2Position";
import { useFormatting } from "~/composables/useFormatting";
import { useSearchFilter } from "~/composables/useSearchFilter";
import { useStatus } from "~/composables/useStatus";
import { useBigNumber } from "~/composables/useBigNumber";
import CardAave from "~/components/protocols/CardAave.vue";
import AaveIcon from "~/assets/icons/aave.svg?inline";
import ButtonCTAOutlined from "~/components/common/input/ButtonCTAOutlined.vue";

export default defineComponent({
  components: {
    BackIcon,
    CardAave,
    AaveIcon,
    ButtonCTAOutlined,
  },
  setup() {
    const {
      position,
      displayPositions,
      totalSupply,
      totalBorrow,
      status,
      liquidation,
      maxLiquidation,
    } = useAaveV2Position();

    const { div } = useBigNumber();

    const statusLiquidationRatio = computed(() =>
      div(status.value, liquidation.value).toFixed()
    );

    const { color, text } = useStatus(statusLiquidationRatio);

    const { formatUsd, formatPercent } = useFormatting();

    const { filtered: filteredPositions, search } = useSearchFilter(
      displayPositions,
      "key",
      "type"
    );

    return {
      position,
      filteredPositions,
      search,
      totalSupply,
      totalBorrow,
      status,
      formatUsd,
      formatPercent,
      color,
      text,
      maxLiquidation,
    };
  }
});
</script>
