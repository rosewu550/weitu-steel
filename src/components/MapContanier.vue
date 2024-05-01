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
        key: "8807bb8f1fc636572f32badadb6e847e", // 申请好的Web端开发者Key，首次调用 load 时必填
        version: "2.0", // 指定要加载的 JSAPI 的版本，缺省时默认为 1.4.15
        plugins: ["AMap.Scale"], //需要使用的的插件列表，如比例尺'AMap.Scale'，支持添加多个如：['...','...']
      })
          .then((AMap) => {
            this.map = new AMap.Map("container", {
              // 设置地图容器id
              viewMode: "3D", // 是否为3D地图模式
              zoom: 11, // 初始化地图级别
              center: [121.418042, 31.355867], // 初始化地图中心点位置
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
  height: 800px;
}

</style>