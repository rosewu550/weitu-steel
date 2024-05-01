<template>
  <div class="news">
    <banner title="COMPANY PERFORMANCE" :img="img"></banner>
    <div class="news-section" v-loading="loading">
      <div class="news-section-content">

        <div class="content-nav-item">

          <div class="item-list" v-for="(item,index) in casesList" :key="index">
            <div v-if="index%2 === 0" class="company-case-even">
              <div class="company-case-title">
                <label :for="index">{{ item.title }}</label>
                <div :id="index" class="case-title-more">
                  <p>more</p>
                  <img :src="require('../assets/img/medium-arrow-black.png')"/>
                </div>
              </div>
              <img :src="item.imgSrc" alt="">
            </div>
            <div v-else class="company-case-odd">
              <img :src="item.imgSrc" alt="">
              <div class="company-case-title">
                <label :for="index">{{ item.title }}</label>
                <div :id="index">more</div>
              </div>
            </div>
          </div>
        </div>


      </div>
    </div>
  </div>
  </div>
</template>

<script>
import Banner from "../components/Banner";

export default {
  name: "news",
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
      casesList: [
        {
          id: 1,
          title: "Capital Airport A380 Hangar Project",
          imgSrc: require("../assets/img/case/airport.png"),
        },
        {
          id: 2,
          title: "No. 218 Test Flight Delivery Hangar Project for Shanghai Aircraft Manufacturing Factory",
          imgSrc: require("../assets/img/case/aircraft factory.png"),
        }
      ],
    };
  }
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}

.news {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;

  &-section {
    width: 100%;
    //height: 1600px;
    &-content {
      width: 1240px;
      margin: 0 auto;

      .content-nav {
        width: 400px;
        height: 55px;
        margin: 0 auto;
        display: flex;
        align-items: center;
        position: relative;
        bottom: 30px;
        border: 1px solid red;

        &-btn {
          width: 50%;
          height: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          background-color: #e4e4e4;
          transition: all 0.2s;
        }

        .content-nav-active {
          background-color: red;
          color: #fff;
        }
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
          height: 70vh;
          display: flex;
          flex-direction: row;
          justify-content: center;

          .company-case-even {
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: flex-end;
            margin: 155px auto;
            text-align: center;

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

            img {
              width: 450px;
              height: 280px;
            }
          }

          .company-case-odd {
            display: flex;
            //justify-content: space-between;
            width: 100%;
            height: 100%;

          }

          &-title {
            width: 300px;
            height: 60px;
            font-size: 22px;
            padding: 0 10px;
            margin: 20px 0;
            overflow: hidden;
            text-overflow: ellipsis;
          }

          &-content {
            width: 273px;
            height: 100px;
            font-size: 14px;
            color: gray;

            // 文本长度处理 begin
            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 5;
            -webkit-box-orient: vertical;
            white-space: normal !important;
            word-wrap: break-word;
            // 文本长度处理 ending
          }

          &-more {
            width: 273px;
            padding-top: 20px;
            display: flex;
            justify-content: flex-start;
            align-items: center;

            img {
              width: 12px;
              height: 12px;
            }

            span {
              color: #e13834;
              padding: 0 5px;
            }
          }
        }
      }
    }
  }

  .text-decoration {
    text-decoration: none;
  }
}
</style>