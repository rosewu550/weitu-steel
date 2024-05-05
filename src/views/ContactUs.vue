<template>
  <div>
    <banner title="CONTACT US" :img="img"></banner>
    <div class="contact-us-container">
      <div class="map-container">
        <MapContainer class="map"></MapContainer>

        <div class="sub-map-container">
          <div class="left-contact-us">
            <div class="left-part left-telephone">
              <img src="../assets/img/telephone.png" alt=""/>
              <div class="left-part-title">telephone:</div>
              <p>13091119111</p>
            </div>
            <div class="left-part left-email">
              <img src="../assets/img/email.png" alt=""/>
              <div class="left-part-title">email:</div>
              <p>912112919191@qq.com</p>
            </div>
          </div>
          <div class="right-contact-us">
            <div class="contact-us-card">
              <div class="card-first">
                <p class="card-title">WEITU STEEL</p>
                <p class="card-sub-title">SHANGHAI WEITU STEEL STRUCTURE ENGINEERING CO., LTD.</p>
              </div>
              <div class="card-second">
                <div class="card-detail">
                  <img class="horizontal-divider" src="../assets/img/horizon-divider.png" alt=""/>
                  <div class="detail-title">
                    <div class="detail-word">address:</div>
                  </div>
                  <div class="detail-title">
                    <div class="detail-word address-detail">
                      Room 902, Building 5, Lane 680, Shuichan West Road, Baoshan District, Shanghai, China
                    </div>
                  </div>
                </div>
                <div class="card-detail">
                  <img class="horizontal-divider" src="../assets/img/horizon-divider.png" alt=""/>
                  <div class="detail-word">post code:</div>
                  <div class="detail-word">200126</div>
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
import MapContainer from "@/components/MapContanier.vue";

export default {
  name: "cpdetail",
  components: {
    MapContainer,
    Banner,
  },
  props: {
    img: {
      type: String,
      default: require("../assets/img/weitu-top2.jpg"),
    },
  },
  data() {
    return {
      pid: -1,
      caseDetailMap: {},
    };
  },
  created() {
    this.pid = this.$route.params.id;
  },
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

.contact-us-container {
  .map-container {
    display: flex;
    flex-direction: column;
    width: 60%;

    margin: 82px auto 50px;
    // overflow: hidden;
    border-radius: 5px;

    .right-contact-us {
      flex: 1;
      position: relative;
    }

    .map{
      min-width: 800px;
    }

    .contact-us-card {
      float: left;
      width: 50%;
      min-width: 500px;
      height: 300px;
      background: rgba(91, 91, 91, 0.9);
      position: absolute;
      right: 0;
      top: -50px;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      row-gap: 25px;
      padding: 40px 50px 0 40px;
      color: #fff;
      box-sizing: border-box;

      .card-title {
        font-size: 15px;
        font-weight: bold;
      }

      .card-sub-title {
        font-size: 20px;
        font-weight: bold;
        width: 100%;
      }

      .card-detail {
        display: flex;
        flex-direction: row;
        column-gap: 10px;
        align-items: center;

        .horizontal-divider {
          align-self: center;
          background: white;
          height: 1px;
        }

        .detail-word {
          height: 100%;
          align-self: center;
        }

        .address-detail {
          width: 100%;
        }
      }

      .card-first {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
      }

      .card-second {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
      }
    }

    .sub-map-container {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column-reverse;

      .left-contact-us {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 80px 0 20px 0;
        width: fit-content;

        .left-part {
          display: flex;
          justify-content: center;
          align-items: center;
          column-gap: 20px;
          font-size: 20px;
          padding: 0 0 40px 0;

          .left-part-title {
            font-size: 22px;
            font-weight: bold;
          }

          img {
            width: 60px;
            height: 60px;
          }
        }
      }
    }
  }
}

@media (max-width: 1416px) {
  .sub-map-container {
    flex-direction: column;
  }
}

@media (max-width: 1480px) and (min-width: 1250px) {
  .contact-us-container .map-container {
    .map{
      min-width: 600px;
      height: 350px !important;
    }

    .contact-us-card{
      min-width: 300px;
    }
  }
}


@media (max-width: 1250px) {
  .contact-us-container .map-container {
    row-gap: 20px;
    width: 90%;

    .map{
      min-width: 200px;
      height: 300px !important;
    }

    .sub-map-container {
      row-gap: 20px;
      .left-contact-us {
        padding: unset;
      }
    }

    .contact-us-card{
      height: 300px;
      min-width: 200px;
      float: unset;
      right: unset;
      top: unset;
      position: relative;
      width: 100%;
    }
  }
}



</style>

