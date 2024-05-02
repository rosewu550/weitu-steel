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
            <img :src="item.imgSrc" alt="">
            <p class="case-item-img-title">{{ item.title }}</p>
            <router-link class="text-decoration" :to="{ name: 'casedetails', params: { id: item.Id } }"></router-link>
          </li>
        </ul>
        <div class="bottom-page">
          <p>more</p>
          <img src="../assets/img/medium-arrow.png"/>
        </div>
      </div>

      <div class="portal-third swiper-slide slide-three">
        <div class="page">
          <h3>CONTACT US</h3>
          <div class="map">
            <MapContainer></MapContainer>
          </div>

          <div class="contact-detail">
            <div class="first-column">
              <label for="address">address:</label>
              <div id="address">Room 902, Building 5, Lane 680, Shuichan West Road, Baoshan District, Shanghai, China
              </div>
            </div>
            <div class="second-column">
              <label for="post-code">post code:</label>
              <div id="post-code">200126</div>

              <label for="telephone">telephone:</label>
              <div id="telephone">13091119111</div>

              <label for="email">email:</label>
              <div id="email">912112919191@qq.com</div>
            </div>
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
    MapContainer
  },
  data() {
    return {
      loading: false,
      caseList: [
        {
          Id: 1,
          imgSrc: "static/img/case/airport.png",
          title: "Aircraft Maintenance Hangar and Annex Construction Project of China Eastern Airlines Kunming New Airport Base"
        },
        {
          Id: 2,
          imgSrc: "static/img/case/park.png",
          title: "Changsha Xingnasi Supply Chain Management Co., Ltd. Changsha Smart Cold Chain Industrial Park Project",
        },
        {
          Id: 3,
          imgSrc: "static/img/case/high.png",
          title: "Suzhou Moon Bay International Center Project"
        },
        {
          Id: 4,
          imgSrc: "static/img/case/shanghai.png",
          title: "Circular Racetrack Project of Jaguar Land Rover",
        },
        {
          Id: 5,
          imgSrc: "static/img/case/football.png",
          title: "Algeria Sports Stadium"
        },
        {
          Id: 6,
          imgSrc: "static/img/case/single.png",
          title: "Chengdu Sancha Lake Changdao International Tourism Resort Project"
        },
      ],
      newsList: [],
      swiperOption: {
        notNextTick: true, //notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
        direction: "vertical", //水平方向移动
        grabCursor: true, //鼠标覆盖Swiper时指针会变成手掌形状，拖动时指针会变成抓手形状
        setWrapperSize: true, //Swiper使用flexbox布局(display: flex)，开启这个设定会在Wrapper上添加等于slides相加的宽或高，在对flexbox布局的支持不是很好的浏览器中可能需要用到。
        autoHeight: true, //自动高度。设置为true时，wrapper和container会随着当前slide的高度而发生变化
        slidesPerView: 1, //设置slider容器能够同时显示的slides数量(carousel模式)。可以设置为数字（可为小数，小数不可loop），或者 'auto'则自动根据slides的宽度来设定数量。loop模式下如果设置为'auto'还需要设置另外一个参数loopedSlides。
        mousewheel: true, //开启鼠标滚轮控制Swiper切换。可设置鼠标选项，默认值false
        mousewheelControl: true, //同上
        height: window.innerHeight - 60, // 高度设置，占满设备高度
        resistanceRatio: 0, //抵抗率。边缘抵抗力的大小比例。值越小抵抗越大越难将slide拖离边缘，0时完全无法拖离。本业务需要
        observeParents: true, //将observe应用于Swiper的父元素。当Swiper的父元素变化时，例如window.resize，Swiper更新

        // 如果自行设计了插件，那么插件的一些配置相关参数，也应该出现在这个对象中，如下debugger
        //debugger: true,

        // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
        on: {
          //监听滑动切换事件，返回swiper对象
          // slideChange: () => {
          //   let swiper = this.$refs.mySwiper.swiper;
          //   //console.log(swiper.activeIndex); //滑动打印当前索引
          //   if (swiper.activeIndex === this.list.length - 1) {
          //     //到最后一个加载更多数据
          //     let newList = [];
          //     let listLength = this.list.length;
          //     for (let i = 0; i < 10; i++) {
          //       newList.push(listLength + i);
          //     }
          //     this.list = this.list.concat(newList);
          //   }
          // }
        },
      },
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

.portal {
  .portal-first {
    height: 100vh !important;
  }

  .portal-second {
    height: 100vh !important;
    padding-top: 94px;
  }

  .portal-third {
    height: 100vh !important;
    padding-top: 94px;
    position: relative;
  }
}

.swiper-slide {
  height: auto;
  font-size: 24px;
  // text-align: center;
  // line-height: 100px;
  //display: ;
  flex-direction: column;
  justify-content: center;
  //align-content: center;

  .page {
    text-align: center;
    //height: 550px;
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
      color: #fff;
    }
  }

  .bottom-page {
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;
    //height: 550px;
    overflow: hidden;
    margin-top: 10px;

    img {
      width: 18px;
      height: 14px;
      margin: 8px 0 0 10px;
    }

    p {
      font-size: 30px;
      //font-weight: bold;
      color: #fff;
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
  .page {
    .map {
      display: block;
      width: 60%;
      height: 600px;
      margin: 82px auto 50px;
      overflow: hidden;
      border-radius: 5px;
    }

    .contact-detail {
      width: 60%;
      display: flex;
      color: white;
      justify-content: space-between;
      margin: 0 auto 50px;
      text-wrap: wrap;
      word-spacing: 10px;
      text-align: left;

      label{
        font-weight: bold;
      }

      .first-column {
        display: flex;
        width: 500px;
        margin-left: 25px;

        #address {
          margin-left: 30px;
        }
      }

      .second-column {
        width: 500px;
        display: grid;
        grid: auto-flow dense / 1fr 3fr;
        margin-right: 25px;

        div {
          margin-left: 30px;
          letter-spacing: 3px;
        }
      }
    }

    h3 {

    }
  }
}

//经典案例
.case-item {
  width: 1100px;
  height: 60vh;
  overflow: hidden;
  margin: 82px auto 82px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  li {
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
    color: white;
    font-size: 15px;
    text-align: center;
  }
}

.slide-one {
  background: url(../assets/img/weitu-top.jpg) no-repeat center;
  background-size: cover;
}

.slide-two {
  background: url(../assets/img/weitu-center-2.png) no-repeat center;
  background-size: cover;
}

.slide-three {
  background: url(../assets/img/weitu_bottom.png) no-repeat center;
  background-size: cover;
}


.order {
  order: -1;
}

.order-img {
  order: 1;
}
</style>

