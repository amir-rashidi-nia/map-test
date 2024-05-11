<template>
  <div class="page">
      <NeshanMap
          defaultType="neshan"
          mapKey="web.3d0e1c00a26e4727ab55d483d0bd7c85"
          serviceKey="service.0a789d697fce4b0697252fe64cb4e4b9"
          :center="{latitude: 36.311559, longitude: 59.5870851}"
          :zoom="14"
          :poi="true"
          :traffic="true"
          @on-init="onInit"
      />
  </div>
</template>
<script setup lang="ts">
import NeshanMap from "@neshan-maps-platform/vue3-openlayers"
import { Map } from "@neshan-maps-platform/ol"
import {fromLonLat} from '@neshan-maps-platform/ol/proj'

function onInit(map:Map) {
    const view = map?.getView()
    view?.animate({
        center: fromLonLat([59.5870851, 36.311559]),
        zoom: 11,
        duration: 1000,
    })
}
</script>
<style>
  @import url("@neshan-maps-platform/vue3-openlayers/dist/style.css");
  html, body, .page, #app {
      width: 100%;
      height: 100%;
      display: block;
      padding: 0;
      margin: 0;
  }
</style>