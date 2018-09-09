<template>
    <div>
        <div id="map" class="map-settings"></div>
    </div>    
</template>
<script>
import L from "leaflet";
export default {
  data() {
    return {
      map: null,
      tileLayer: null
    };
  },
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      this.map = L.map("map", {
        center: [25.0419643, 121.5320798],
        zoom: 10
      });
      this.tileLayer = L.tileLayer(
        "https://cartodb-basemaps-{s}.global.ssl.fastly.net/rastertiles/voyager_labels_under/{z}/{x}/{y}{r}.png",
        {
          attribution:
            '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> &copy; <a href="http://cartodb.com/attributions">CartoDB</a>',
          subdomains: "abcd",
          maxZoom: 19
        }
      ).addTo(this.map);
    }
  }
};
</script>
<style>
.map-settings {
  height: 600px;
  width: 100%;
}
</style>
