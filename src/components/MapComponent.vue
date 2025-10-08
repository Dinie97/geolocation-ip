<script setup lang="ts">
import LeafletMap from "./LeafletMap.vue";
defineProps<{ msg: string }>();
</script>

<template>
  <div class="relative z-0">
    <!-- Background image -->
    <!-- <img
      src="../assets/images/pattern-bg-desktop.png"
      alt="Background"
      class="w-full h-full"
    /> -->

    <!-- Mobile image -->
    <img
      src="../assets/images/pattern-bg-mobile.png"
      class="block sm:hidden w-full"
      alt="Mobile Image"
    />

    <!-- Desktop image -->
    <img
      src="../assets/images/pattern-bg-desktop.png"
      class="hidden lg:block w-full"
      alt="Desktop Image"
    />

    <!-- Text on top -->
    <div class="absolute inset-0 flex items-center justify-center flex-col">
      <h2 class="text-white text-2xl font-bold">IP Address Tracker</h2>

      <div
        class="flex w-full max-w-md overflow-hidden rounded-full bg-white shadow-md m-8"
      >
        <input
          type="text"
          placeholder="Search for any IP address or domain"
          class="flex-1 px-5 py-3 text-sm text-gray-700 placeholder-gray-400 focus:outline-none"
        />
        <button
          type="button"
          class="flex items-center justify-center bg-black px-5 text-white transition hover:bg-gray-800"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-4 w-4"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M9 5l7 7-7 7"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>

  <div
    class="absolute inset-0 flex items-center justify-center flex-col z-5 mb-30"
  >
    <div class="flex flex-row rounded-sm bg-white w-6xl">
      <!-- <div class="p-6 border-r-20 border-gray-200">
        <p class="text-xs text-gray-400 uppercase">IP Address</p>
        <p class="text-lg font-bold text-black">192.168.1.1</p>
      </div> -->

      <div class="grid grid-cols-4 divide-x-2 divide-gray-200 w-full p-4">
        <div class="p-4">
          <h6 class="text-base text-gray-600 font-medium mb-4">IP ADDRESS</h6>
          <h1 class="text-3xl font-medium">192.110.221.932</h1>
        </div>

        <div class="p-4">
          <h6 class="text-base text-gray-600 font-medium mb-4">LOCATION</h6>
          <h1 class="text-2xl font-medium">Kuala Lumpur, MY, 47301</h1>
        </div>
        <div class="p-4">
          <h6 class="text-base text-gray-600 font-medium mb-4">TIMEZONE</h6>
          <h1 class="text-2xl font-medium">UTC -05:00</h1>
        </div>
        <div class="p-4">
          <h6 class="text-base text-gray-600 font-medium mb-4">ISP</h6>
          <h1 class="text-2xl font-medium">SpaceX Starlink</h1>
        </div>
      </div>
    </div>
  </div>
  <div class="relative w-full h-screen z-0">
    <LeafletMap />
  </div>
</template>

<style scoped></style>
