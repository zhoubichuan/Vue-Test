<template>
    <div ref="map" class="map"></div>
  </template>
  <script>
  export default {
    mounted() {
      let {
        Map,
        View,
        layer: { WebGLTile: TileLayer },
        source: { OSM },
      } = ol
      new Map({
        target: this.$refs.map,
        layers: [
          new TileLayer({
            source: new OSM(),
            minZoom: 4,
            maxZoom: 12,
          }),
        ],
        view: new View({
          center: [12579156, 3274244],
          zoom: 12,
        }),
      })
    },
  }
  </script>