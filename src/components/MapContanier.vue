<template>
  <div id="container"></div>
</template>

<script>
import AMapLoader from "@amap/amap-jsapi-loader";

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
      }).then((AMap) => {
        this.map = new AMap.Map("container", {
          viewMode: "3D",
          zoom: 10,
          center: [121.418042, 31.355867],
          mapStyle: "amap://styles/whitesmoke",
        });

        const icon = new AMap.Icon({
          size: new AMap.Size(24,24),
          image:"favicon.ico",
          imageOffset:new AMap.Pixel(0,0),
          imageSize: new AMap.Size(24,24)
        })

        const marker = new AMap.Marker({
          position: new AMap.LngLat(121.418042, 31.355867),
          icon:icon,
          title:"weitu steel",
          label: {
            content: "WEITU STEEL",
            direction: 'right'
          },
        });
        this.map.add(marker);
      });
    },
  },
};
</script>

<style lang="scss">
#container {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 500px;

  .amap-marker-label{
    border: 0;
    font-weight: bold;
    background-color: transparent;
  }
}

@media (max-width: 800px) {
  #container{
    height: 250px;
  }
}
</style>

