<template>
  <div>
    <banner title="COMPANY PERFORMANCE" :img="img"></banner>
    <div class="case-detail">
      <div class="case-detail-item">
        <img :src=caseDetailMap.imgSrc alt="">
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
    Banner
  },
  props: {
    img: {
      type: String,
      default: require("../assets/img/companyPerformance.png")
    }
  },
  data() {
    return {
      pid: -1,
      caseDetailMap: {}
    };
  },
  created() {
    this.pid = this.$route.params.id;
  },
  mounted() {
    this.$http.get('static/json/companyCase.json').then(response => {
      const casesList = response.data;
      this.caseDetailMap = casesList.filter(caseMap => {
        if (this.pid === caseMap.id) {
          return caseMap;
        }
      })[0];
    })
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

  img {
    width: 60%;
    height: 600px;
    padding-bottom: 10vh;
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

</style>