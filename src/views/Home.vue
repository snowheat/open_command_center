<template>
  <div class="home">
    <div id="viewDiv"></div>
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
          basemap: 'streets',
        });
        // and we show that map in a container w/ id #viewDiv
        const view = new MapView({
          map: webmap,
          container: 'viewDiv',
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
#viewDiv {
  width: 1000px;
  height: 600px;
  background: gray;
}
</style>

