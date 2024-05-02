<template>
  <div class="news">
    <banner title="COMPANY PERFORMANCE" :img="img"></banner>
    <div class="news-section" v-loading="loading">
      <div class="news-section-content">

        <div class="content-nav-item">
          <div class="item-list" v-for="(item,index) in casesList" :key="index">
            <div v-if="index%2 === 0" class="company-case company-case-even">
              <div class="company-case-title">
                <label :for="index">{{ item.title }}</label>
                <div :id="index" class="case-title-more">
                  <router-link
                      class="text-decoration"
                      :to="{ name: 'cpdetail', params: { id: item.title }}"
                  >
                    <p>more</p>
                    <img :src="require('../assets/img/medium-arrow-black.png')"/>
                  </router-link>
                </div>
              </div>
              <img :src=item.imgSrc alt="">
            </div>
            <div v-else class="company-case company-case-odd">
              <img :src=item.imgSrc alt="">
              <div class="company-case-title">
                <label :for="index">{{ item.title }}</label>
                <div :id="index" class="case-title-more">
                  <router-link
                      class="text-decoration"
                      :to="{ name: 'cpdetail', params: { id: item.title }}"
                  >
                    <p>more</p>
                    <img :src="require('../assets/img/medium-arrow-black.png')"/>
                  </router-link>
                </div>
              </div>
            </div>
            <div class = "company-case-divider"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "../components/Banner";

export default {
  name: "company-performance",
  components: {
    Banner
  },
  props: {
    casesList:[],
    img: {
      type: String,
      default: require("../assets/img/companyPerformance.png")
    }
  },
  mounted() {
    this.$http.get('static/json/companyCase.json').then(response => {
      this.casesList = response.data;
    })
  }
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}

.content-nav-item {
  width: 1070px;
  margin: 0 auto;
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  //border: 1px solid blue;

  .item-list {
    width: 100%;
    height: 60vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    padding-top: 20vh;


    .company-case {
      width: 100%;
      height: 100%;
      display: flex;
      margin: 0 auto;
      text-align: center;

      img {
        width: 450px;
        height: 280px;
      }
    }

    .company-case-title {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      margin: 30px 0;
      width: 100%;
      height: 220px;

      label {
        width: 50%;
        font-weight: bold;
        font-size: 25px;
        text-align: center;
        margin: 0 auto;
      }

      .case-title-more {
        display: flex;
        overflow: hidden;
        font-size: 25px;
        text-align: center;
        justify-content: center;
        align-items: center;

        img {
          width: 18px;
          height: 14px;
          margin: 5px 0 0 10px;
        }
      }
    }

    .company-case-even {
      justify-content: flex-end;
    }

    .company-case-odd {
      justify-content: flex-start;
    }

    .company-case-divider{
      display: flow;
      width: 100vw;
      height: 2px;
      background: #D9D9D9;
      //border: 1px solid #D9D9D9;
      border-radius: 10px;
      position: relative;
      left: 50%;
      transform: translateX(-50%);
    }
  }
}
</style>