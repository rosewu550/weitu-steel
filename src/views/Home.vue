<template>
  <div class="home" v-loading="loading">
    <div class="portal swiper-slide">
      <div class="portal-first swiper-slide slide-one">
        <div class="page">
          <p class="big-slogan">PROFESSIONALISM QUALITY INTEGRITY</p>
        </div>
      </div>

      <div class="portal-second swiper-slide slide-two">
        <div class="page">
          <h3>COMPANY PERFORMANCE</h3>
        </div>
        <ul class="case-item">
          <li v-for="(item, index) in caseList" :key="index">
            <router-link
                class="text-decoration"
                :to="{ name: 'cpdetail', params: { id: item.id }}"
            >
              <img :src="item.imgSrc" alt=""/>
              <p class="case-item-img-title">{{ item.title }}</p>
            </router-link>
          </li>
        </ul>
        <router-link
            class="text-decoration"
            :to="{ name: 'companyPerformance'}"
        >
          <div class="bottom-page">
            <p>more</p>
            <img src="../assets/img/medium-arrow-black.png"/>
          </div>
        </router-link>
      </div>

      <div class="portal-third swiper-slide slide-three">
        <div class="contact-us-page">
          <div class="contact-left">
            <div class="contact-detail">

              <div class="first-column">
                <label class="address-label" for="address">address:</label>
                <div id="address">
                  Room 902, Building 5, Lane 680, Shuichan West Road, Baoshan District, Shanghai, China
                </div>
              </div>
              <div class="second-column">
                <label for="post-code">post code:</label>
                <div id="post-code">201900</div>

                <label for="telephone">telephone:</label>
                <div id="telephone">18601733332</div>

                <label for="email">email:</label>
                <div id="email">xaerpg@163.com</div>
              </div>
            </div>
              <router-link
                  class="text-decoration contact-us-title"
                  :to="{ name: 'contactus'}"
              >
                <p >CONTACT US</p>
                <img src="../assets/img/medium-arrow.png"/>
              </router-link>
          </div>
          <div class="map">
            <MapContainer></MapContainer>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MapContainer from "../components/MapContanier.vue";

export default {
  name: "HelloWorld",
  components: {
    MapContainer,
  },
  data() {
    return {
      loading: false,
      caseList: [
        {
          "title": "Aircraft Maintenance Hangar and Annex Construction Project of China Eastern Airlines Kunming New Airport Base",
          "imgSrc": "static/img/case/airport.png",
          "id": "2",
        },
        {
          "title": "Changsha Xingnasi Supply Chain Management Co., Ltd. Changsha Smart Cold Chain Industrial Park Project",
          "imgSrc": "static/img/case/park.png",
          "id": "22",
        },
        {
          "title": "Suzhou Moon Bay International Center Project",
          "imgSrc": "static/img/case/high.png",
          "id": "20",
        },
        {
          "title": "Circular Racetrack Project of Jaguar Land Rover",
          "imgSrc": "static/img/case/shanghai.png",
          "id": "7",
        },
        {
          "title": "Algeria Sports Stadium",
          "imgSrc": "static/img/case/football.png",
          "id": "41",
        },
        {
          "title": "Chengdu Sancha Lake Changdao International Tourism Resort Project",
          "imgSrc": "static/img/case/single.png",
          "id": "11",
        }
      ],
      newsList: [],
    };
  },
  created() {
  },
  // 如果你需要得到当前的swiper对象来做一些事情，你可以像下面这样定义一个方法属性来获取当前的swiper对象，同时notNextTick必须为true
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper;
    },
  },
};
</script>

<style lang="scss" scoped>

.text-decoration {
  text-decoration: none;
}

.portal {
  max-width: 100%;

  .portal-first {
    min-height: 100dvh !important;
  }

  .portal-second {
    min-height: 100svh !important;
    padding-top: 94px;
  }

  .portal-third {
    min-height: 100dvh !important;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.swiper-slide {
  height: auto;
  font-size: 24px;
  overflow: hidden;
  flex-direction: column;
  justify-content: center;

  .page {
    text-align: center;
    overflow: hidden;

    .big-slogan {
      font-size: 40px;
      font-weight: bold;
      color: #fff;
    }

    h3,
    p {
      font-size: 30px;
      font-weight: bold;
      color: black;
    }
  }

  .bottom-page {
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;
    //height: 550px;
    overflow: hidden;
    margin-bottom: 82px;

    img {
      width: 18px;
      height: 14px;
      margin: 8px 0 0 10px;
    }

    p {
      font-size: 30px;
      //font-weight: bold;
      color: black;
      position: relative;
    }
  }

  .slogan {
    text-align: center;
    font-size: 50px;
    color: #fff;
    padding: 30px 0;
  }
}

.swiper-slide .slide-one {
  align-content: center;
}

.portal-third {
  .contact-us-page{
    width: 60%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 50px;
    justify-content: center;

    .contact-us-title {
      display: flex;
      color: #fff;
      p {
        font-weight: bold;
      }

      img {
        width: 18px;
        height: 14px;
        margin: 8px 0 0 10px;
      }
    }

    .contact-left{
      align-self: center;
      justify-self: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      row-gap: 100px;

      .contact-detail {
        width: 100%;
        min-width: 350px;
        display: flex;
        flex-wrap: wrap;
        color: white;
        justify-content: flex-start;
        //margin: 0 auto 50px;
        text-wrap: wrap;
        text-align: left;
        row-gap: 20px;

        label {
          min-width: 130px;
          font-weight: bold;
        }

        .first-column {
          display: grid;
          grid-template-columns: 1fr 4fr;
          //grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
          //width: 45%;
          min-width: 300px;
          text-align: start;

          .address-label{
            margin-bottom: 20px;
          }
        }

        .second-column {
          width: 50%;
          display: grid;
          grid-template-columns: 1fr 3fr;
          column-gap: 1rem;
          text-align: start;
          row-gap: 20px;

        }
      }

    }


    .map {
      display: block;
      width: 100%;
      overflow: hidden;
      border-radius: 5px;
    }


  }
}

//经典案例
.case-item {
  width: 60%;
  overflow: hidden;
  margin: 82px auto 82px;
  display: grid;
  row-gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(30%, 1fr));
  justify-content: center;

  li {
    justify-self: center;
    width: 330px;
    height: 250px;
    list-style: none;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    background-origin: content-box;
    margin: 5px;
    position: relative;
    overflow: hidden;

    &:hover {
      .case-item-hover {
        opacity: 1;
        transition: all 0.4s ease-in-out;
      }
    }
  }

  img {
    display: block;
    max-width: 100%;
    height: auto;
    border-radius: 5px;
  }

  .case-item-img-title {
    margin-top: 5px;
    color: black;
    font-size: 15px;
    text-align: center;
  }
}

.slide-one {
  background: url(../assets/img/weitu-top2.jpg) no-repeat center;
  background-size: cover;
}

.slide-two {
  //background: url(../assets/img/weitu-center-2.png) no-repeat center;
  //background-size: cover;
}

.slide-three {
  background: url(../assets/img/weitu-center-2.png) no-repeat center;
  background-size: cover;
}

.order {
  order: -1;
}

.order-img {
  order: 1;
}

@media (max-width: 680px) {
  .case-item {
    width: 100%;
  }
}

@media (min-width: 1000px) and (max-width: 1800px) {
  .case-item {
    grid-template-columns: repeat(auto-fit, minmax(50%, 1fr));
  }
}

@media (max-width: 1000px) {
  .case-item {
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  }

  .portal-third .page .contact-detail{
    justify-content: flex-start;
    .first-column {
      width: 100%;
    }
  }

  .portal-third .contact-us-page {
    grid-template-columns: 1fr;
    width: 100%;


    .contact-left{
      order: 2;
      align-self: center;
      height: 400px;
      row-gap: 50px;
      width: 80%;

    }

    .map{
      width: 80%;
      order: 1;
      height: 80%;
      align-self: center;
      justify-self: center;
    }

  }
}


@media (max-width: 400px) {
  .case-item {
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  }

  .portal-third .page .contact-detail{
    justify-content: center;
    .second-column{
      width: 100%;
      text-align: center;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    }

    .first-column {
      text-align: center;
      margin-inline: auto;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    }
  }
}

@media (max-width: 800px) {
  .portal-third .page .map{
    width: 75%;
  }
}

@media (max-width: 400px) {
  .portal-third .page .map{
    width: 90%;
  }
}

@media (max-width: 1500px) and (min-width: 1000px) {
  .portal-third .contact-us-page {
    width: 80%;
  }
}



</style>

