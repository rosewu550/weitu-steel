<template>
  <div id="container"></div>
</template>


<script>
import AMapLoader from '@amap/amap-jsapi-loader';

export default {
  name: "map-view",
  mounted() {
    this.initAMap();
  },
  methods: {
    initAMap() {
      window._AMapSecurityConfig = {
        securityJsCode: "fe24e49cfd4c4e4a99899a46e5816e0f",
      };
      AMapLoader.load({
        key: "8807bb8f1fc636572f32badadb6e847e",
        version: "2.0",
        plugins: ["AMap.Scale"],
      })
          .then((AMap) => {
            this.map = new AMap.Map("container", {
              viewMode: "3D",
              zoom: 11,
              center: [121.418042, 31.355867],
              mapStyle: "amap://styles/whitesmoke",
            });

            const marker = new AMap.Marker({
              position: new AMap.LngLat(121.418042, 31.355867),
              label:{
                "content":"WEITU STEEL"
              }
            });
            this.map.add(marker);
          });
    },
  },
};

</script>


<style lang="scss" scoped>
#container {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
}

</style>