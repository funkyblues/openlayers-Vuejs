<template>
  <div id="map"></div>
</template>

<script>
import { Map, View } from "ol";
import { Tile as TileLayer } from "ol/layer";
import { OSM } from "ol/source";
import { fromLonLat } from "ol/proj";

export default {
  name: "Map",
  mounted() {
    this.map = new Map({
      target: "map",
      layers: [
        new TileLayer({
          source: new OSM(),
        }),
      ],
      view: new View({
        center: fromLonLat([127.1388684, 37.4449168]),
        zoom: 10,
      }),
    });
  },
};
</script>

<style></style>
