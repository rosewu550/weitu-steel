<template>
  <div class="company-performance">
    <banner class="banner" title="COMPANY PERFORMANCE" :img="img"></banner>
    <div class="content-nav-item">
      <div class="item-list" v-for="(item,index) in casesList" :key="index">
        <div v-if="index%2 === 0" class="company-case company-case-even">
          <div class="company-case-title">
            <label :for="index">{{ item.title }}</label>
            <div :id="index" class="case-title-root">
              <router-link
                  class="text-decoration case-title-more"
                  :to="{ name: 'cpdetail', params: { id: item.id }}"
              >
                <p>more</p>
                <img :src="require('../assets/img/medium-arrow-black.png')" alt=""/>
              </router-link>

            </div>
          </div>
          <img :src=item.imgSrc alt="">
        </div>
        <div v-else class="company-case company-case-odd">
          <img :src=item.imgSrc alt="">
          <div class="company-case-title">
            <label :for="index">{{ item.title }}</label>
            <div :id="index" class="case-title-root">
              <router-link
                  class="text-decoration case-title-more"
                  :to="{ name: 'cpdetail', params: { id: item.id }}"
              >
                <p>more</p>
                <img :src="require('../assets/img/medium-arrow-black.png')"/>
              </router-link>
            </div>
          </div>
        </div>
        <div class="company-case-divider"></div>
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
  data(){
    return {
      casesList: [],
    };
  },
  props: {
    img: {
      type: String,
      default: require("../assets/img/weitu-top2.jpg")
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

.text-decoration {
  text-decoration: none;
}

.banner {
  margin-bottom: 10vh;
}

.content-nav-item {
  width: 60%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  flex-wrap: wrap;


  .item-list {
    width: 100%;
    //height: 50vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    margin: 50px 0 100px 0;

    .company-case {
      width: 100%;
      height: 100%;
      display: flex;
      margin: 0 auto;
      text-align: center;

      img {
        width: 100%;
        max-width: 450px;
        max-height: 280px;
      }
    }

    .company-case-title {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      margin: 30px 0;
      row-gap: 50%;
      width: 100%;
      height: 220px;

      label {
        width: 50%;
        font-weight: bold;
        font-size: 25px;
        text-align: center;
        margin: 0 auto;
      }

      .case-title-root {
        display: flex;
        justify-content: center;
      }

      .case-title-more {
        display: flex;
        overflow: hidden;
        font-size: 25px;
        text-align: center;
        justify-content: center;
        align-items: center;
        color: black;

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

    .company-case-divider {
      display: none;
      //display: flow;
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


@media (max-width: 1000px) {
  .content-nav-item .item-list .company-case{
    flex-direction: column;
    justify-content: center;
    align-items: center;


    .content-nav-item .item-list .company-case-title label{
      width: 100%;
    }
  }

  .content-nav-item .item-list .company-case-even{
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }

}

@media (max-width: 1400px) {
  .content-nav-item .item-list{
    row-gap: 0;
    padding-top:0;

  }


  .content-nav-item .item-list .company-case-title{

    label{
      font-size: 20px;
      width: 80%;
    }
  }
}

@media (max-height: 700px) {
  .content-nav-item{
    margin-top: 20px;
  }

  .content-nav-item .item-list .company-case-title{
    //row-gap: 20%;

    label{
      font-size: 20px;
      width: 100%;
    }
  }
}








</style>