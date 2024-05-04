<template>
  <div class="banner">
    <div class="mm"></div>
    <div class="banner-img">
      <img :src="img"/>
    </div>
    <div class="banner-title">
      <p>{{ title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  props: {
    title: {
      type: String,
      default: ""
    },
    img: {
      type: String,
      default: require("../assets/img/weitu-top.jpg")
    }
  }
};
</script>

<style lang="scss" scoped>
.banner {
  width: 100%;
  height: 500px;
  display: flex;
  position: relative;
  overflow: hidden;
  background-color: #fff;

  .mm {
    position: absolute;
    width: 100%;
    height: 100%;

    padding: 10px;
    margin: -10px;
    filter: blur(10px);

    background-image: url(../assets/img/weitu-top.jpg);
    background-position: center;
    background-size: 100%;
  }

  img {
    position: absolute;
    //width: 1240px;
    margin-top:70px;
    width: 100%;
    height: 100%;
    left: 50%;
    transform: translate(-50%, 0);
  }

  &-title {
    position: absolute;
    padding-top:140px;
    color: #fff;
    font-size: 45px;
    font-weight: bold;
    line-height: 300px;
    text-align: center;
    width: 100%;
  }
}
</style>