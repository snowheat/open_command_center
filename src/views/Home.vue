<template>
  <div id="home" class="columns">
    <div id="right-sidebar" class="column">
      <div class="columns is-multiline">
        <div id="right-sidebar-menu" class="column">
          <h3>Menu</h3>
          <div class="select">
            <select>
              <option value="">Keluhan - LAPOR</option>
              <option value="">CCTV</option>
              <option value="">Potensi Desa</option>
              <option value="">Infrastruktur</option>
              <option value="">Pemerintahan</option>
            </select>
          </div>
        </div>
      </div>
    </div>
    <div id="map" class="column">
      <div class="columns">
        <div class="column">
          <div id="view-div"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import * as esriLoader from 'esri-loader';

export default {
  name: 'home',
  components: {
    HelloWorld,
  },
  created() {
    esriLoader.loadModules(['esri/views/MapView', 'esri/Map'], {})
      .then(([MapView, Map]) => {
        // then we load a web map from an id
        const webmap = new Map({
          basemap: 'satellite',
        });
        // and we show that map in a container w/ id #viewDiv
        const view = new MapView({
          map: webmap,
          container: 'view-div',
          zoom: 4,
          center: [15, 65],
        });

        console.log(view);
      })
      .catch((err) => {
        // handle any errors
        console.error(err);
      });
  },
};
</script>

<style lang="less">
@import url('../assets/less/home');
</style>
