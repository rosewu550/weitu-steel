<template>
  <div class="banner">
    <div class="mm"></div>
    <div class="banner-img">
      <img :src="img"/>
    </div>
    <div class="banner-title">
      <div>{{ title }}</div>
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
  height: 40dvh;
  min-height: 300px;
  display: flex;
  flex-direction: column;
  //justify-content: center;
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
    bottom: 30%;
    color: #fff;
    font-size: 45px;
    font-weight: bold;
    text-align: center;
    width: 100%;
  }
}

@media (max-width: 570px) {
  .banner-title{
    font-size: 35px;
  }
}

@media (max-width: 433px) and (max-height: 800px) {
  .banner-title{
    bottom: 20%;
  }
}

@media (max-width: 433px) and (min-height: 800px) and (max-height: 1000px) {
  .banner-title{
    bottom: 25%;
  }
}

@media (min-height: 1000px) {
  .banner-title{
    bottom: 35%;
  }
}


</style>