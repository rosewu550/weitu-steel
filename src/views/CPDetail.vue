<template>
  <div>
    <banner title="COMPANY PERFORMANCE" :img="img"></banner>
    <div class="case-detail">
      <div class="case-detail-item">

        <div class="case-detail-swiper">
          <el-carousel :height="carouselHeight" interval=5000 indicator-position="outside">
            <el-carousel-item v-for="item in caseDetailMap.imgSrcArr" :key="item">
              <img :src=item alt="">
            </el-carousel-item>
          </el-carousel>
        </div>

        <p class="item-title">{{ caseDetailMap.title }}</p>
        <p class="item-content">Project location: {{ caseDetailMap.projectLocation }}</p>
        <p class="item-content">Construction unit: {{ caseDetailMap.constructionUnit }}</p>
        <p class="item-content">Project scope: {{ caseDetailMap.projectScope }}</p>
        <p class="item-content">Project scale: {{ caseDetailMap.projectScale }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "../components/Banner";

export default {
  name: "cpdetail",
  components: {
    Banner,
  },
  props: {
    img: {
      type: String,
      default: require("../assets/img/companyPerformance.png")
    }
  },
  data() {
    return {
      carouselHeight: "600px",
      pid: -1,
      caseDetailMap: {}
    };
  },
  created() {
    this.pid = this.$route.params.id;
    let _$nextTick = this.$nextTick;
    this.$nextTick(() => {
      _$nextTick();
      const screenWide = window.innerWidth || document.documentElement.clientWidth;
      const isWideScreen = screenWide >= 1000;
      this.carouselHeight = isWideScreen ? "600px" : "300px";
    })
  },
  mounted() {
    let _windowOnresize = window.onresize;
    window.onresize = () => {
      _windowOnresize();
      const screenWide = window.innerWidth || document.documentElement.clientWidth;
      const isWideScreen = screenWide >= 1000;
      this.carouselHeight = isWideScreen ? "600px" : "300px";
    }

    this.$http.get('static/json/companyCase.json').then(response => {
      const casesList = response.data;
      this.caseDetailMap = casesList.filter(caseMap => {
        if (this.pid === caseMap.id) {
          return caseMap;
        }
      })[0];
    });
  }
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}

.text-decoration {
  text-decoration: none;
}

.case-detail {
  width: 100%;
  height: 100%;
  margin: 0 auto 200px;

}

.case-detail-item {
  padding-top: 20vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: left;

  .case-detail-swiper {
    width: 60%;
    padding-bottom: 10vh;
  }

  img {
    width: 100%;
    height: 100%;

  }

  .item-title {
    width: 60%;
    font-weight: bold;
    font-size: 25px;
    padding-bottom: 50px;
  }

  .item-content {
    width: 60%;
    font-size: 20px;
  }
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}

</style>