<template>
  <div id="map" class="w-full h-96 rounded-lg shadow-md"></div>
</template>

<script setup>
import { onMounted } from "vue";
import L from "leaflet";

onMounted(() => {
  // Initialize the map
  // const map = L.map("map").setView([3.139, 101.6869], 13);
  const map = L.map("map", {
    center: [51.505, -0.09],
    zoom: 13,
    doubleClickZoom: false,
    scrollWheelZoom: false,
    touchZoom: false,
    boxZoom: false,
    keyboard: false,
    zoomControl: false, // hides the +/- buttons
  });

  map.setView([3.139, 101.6869], 13);

  // Add OpenStreetMap tiles
  L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
    attribution:
      '&copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors',
  }).addTo(map);

  // Add a marker
  L.marker([3.139, 101.6869])
    .addTo(map)
    .bindPopup("<b>Hello!</b><br>This is Kuala Lumpur.")
    .openPopup();
});
</script>

<style scoped>
#map {
  height: 60%;
  width: 100%;
}
</style>
