<template>
  <div>
    <banner title="CONTACT US" :img="img"></banner>
    <div class="contact-us-container">
      <div class="map-container">
        <MapContainer class="map"></MapContainer>
        <div class="sub-map-container">
          <div class="contact-us-card">
            <p class="card-title">WEITU STEEL</p>
            <p class="card-sub-title">SHANGHAI WEITU STEEL STRUCTURE ENGINEERING CO., LTD.</p>
            <div class="card-detail">
              <img class="horizontal-divider" src="../assets/img/horizon-divider.png" alt="">
              <div class="detail-title">
                <div class="detail-word">address:</div>
              </div>
              <div class="detail-title">
                <div class="detail-word address-detail">Room 902, Building 5, Lane 680, Shuichan West Road, Baoshan
                  District, Shanghai, China
                </div>
              </div>

            </div>
            <div class="card-detail">
              <img class="horizontal-divider" src="../assets/img/horizon-divider.png" alt="">
              <div class="detail-word">post code:</div>
              <div class="detail-word">200126</div>
            </div>
          </div>
          <div class="left-contact-us">
            <div class="left-part left-telephone">
              <img src="../assets/img/telephone.png" alt="">
              <div class="left-part-title">telephone:</div>
              <p>13091119111</p>
            </div>
            <div class="left-part left-email">
              <img src="../assets/img/email.png" alt="">
              <div class="left-part-title">email:</div>
              <p>912112919191@qq.com</p>
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
  mounted() {
    this.$http.get("static/json/companyCase.json").then((response) => {
      const casesList = response.data;
      this.caseDetailMap = casesList.filter((caseMap) => {
        if (this.pid === caseMap.id) {
          return caseMap;
        }
      })[0];
    });
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
  position: relative;
  .map-container {
    display: flex;
    flex-direction: column;
    width: 60%;
    height: 900px;
    margin: 82px auto 50px;
    overflow: hidden;
    border-radius: 5px;

    .map {
      height: 500px;
    }

    .contact-us-card {
      float: left;
      width: 30%;
      height: 40%;
      background: rgba(91, 91, 91, 0.9);
      position: absolute;
      right: 110px;
      bottom: 0;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      padding: 40px 0 0 50px;
      color: #fff;
      box-sizing: border-box;

      .card-title {
        font-size: 16px;
        font-weight: bold;
      }

      .card-sub-title {
        font-size: 20px;
        font-weight: bold;
        margin-top: 15px;
        width: 90%;

      }

      .card-detail {
        display: flex;
        flex-direction: row;
        margin-top: 30px;

        .horizontal-divider {
          background: white;
          height: 1px;
          position: relative;
          top: 50%;
          transform: translateY(-50%);
        }

        .detail-word {
          margin: 0 20px 15px 10px;
          // height: 30px;
          position: relative;
          top: 50%;
          transform: translateY(-50%);
        }

        .address-detail {
          width: 70%;
          margin: 0 50px 0 23px;
        }
      }
    }

    .sub-map-container {
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: flex-start;

      .left-contact-us {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        position: absolute;
        float: left;
        padding: 80px 0 20px 0;


        .left-part {
          display: flex;
          justify-content: center;
          align-items: center;
          column-gap: 20px;
          font-size: 20px;
          padding: 0 0 40px 0;

          .left-part-title{
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
</style>


</style>
