<template>
  <div>
    <banner title="ABOUT WEITU" :img="img"></banner>
    <div class="about-weitu">
      <div class="about-weitu-menu">
        <div class="menu-logo">ABOUT WEITU</div>
        <div class="vertical-divider"></div>
        <div class="menu-content">
          <div class="menu-content-detail">
            <p @click="selectMenu" :class="{'menu-content-selected':menuSelected==='company-profile-menu'}"
               id="company-profile-menu">Company profile</p>
            <p @click="selectMenu" :class="{'menu-content-selected':menuSelected==='construction-management-menu'}"
               id="construction-management-menu">Construction management</p>
            <p @click="selectMenu" :class="{'menu-content-selected':menuSelected==='overview-of-plant-menu'}"
               id="overview-of-plant-menu">Overview of plant</p>
          </div>
        </div>
      </div>

      <div class="about-weitu-body">
        <div v-if="menuSelected === 'construction-management-menu' " id="construction-management-body">
          <div class="profile-body-even">
            <div class="body-even-title">Safety objectives</div>
            <div class="body-even-center">
              <p>Ensure the prevention of major safety incidents and achieve zero lost-time accidents.
                It is imperative that every individual adheres strictly to the safety regulations and standards
                established by the company for each project, ensuring 100% compliance.
                Immediate rectification is required for any identified unsafe factors, and strict measures will be taken
                for any single violation.</p>
            </div>
          </div>

          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Safety, civility, and security management system</p>
            </div>
            <div class="center-construction-management">
              <p>Our top priorities revolve around integrity, professionalism, efficiency, quality, and ensuring
                customer satisfaction!</p>
              <p>I. Safety management system</p>
              <p>II. Safety production management system</p>
              <p>III. Laws, regulations and normative documents</p>
              <p>IV. Hazardous sources management</p>
              <p>V. Utilization and oversight of special safety funds</p>
              <p>Ⅵ. Safety production technology measures</p>
              <p>VII. Safety control measures for major sub-projects</p>
              <p>VIII. Basic requirements and norms for the construction site</p>
              <p>IX. Management and control of high-risk operations</p>
              <p>X. Safety education and training</p>
              <p>XI. Safety activities</p>
              <p>XII. Safety management of general contractor and subcontractor</p>
              <p>XIII. Safety inspection and identification of hidden hazards</p>
              <p>XIV. Construction machinery management</p>
              <p>XV. Reward and punishment system and rules</p>
              <p>XⅥ. Accident handling and report analysis</p>
              <p>XVII. Fire control</p>
              <p>XVIII. Plan of civilized construction measures</p>
              <p>XIX. Security plans and measures</p>

            </div>
          </div>


        </div>


        <div v-else-if="menuSelected === 'overview-of-plant-menu'" id="overview-of-plant-body"></div>
        <div v-else id="company-profile-body">
          <div class="profile-body-even">
            <div class="body-even-title">introduction</div>
            <div class="body-even-center">
              <div class="body-even-left">
                <p>Established in 2005, Shanghai Weitu Steel Structure Engineering Co., Ltd.is a domestic joint venture
                  limited liability company with a registered capital of 10 million yuan. Currently, the company boasts
                  a team of over 30 skilled professionals specializing in steel structure engineering.
                  Our core activities include the production and installation of steel structures, net frame structures,
                  and steel structure enclosure systems. We also offer specialized services in steel structure design
                  and detailed drawing refinement.
                </p>
              </div>
              <div class="body-even-right">
                <img src="static/img/aboutweitu/image11.png" alt="">
              </div>
            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Operation philosophy</p>
            </div>
            <div class="body-odd-center">
              <div class="body-odd-left">
                <img src="../assets/img/OperationPhilosophy.png" alt="">
              </div>
              <div class="body-odd-right">
                <p>Our top priorities revolve around integrity, professionalism, efficiency, quality, and ensuring
                  customer satisfaction!</p>
              </div>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">Service objectives</div>
            <div class="body-even-center">
              <div class="body-even-right">
                <img src="../assets/img/serviceObjectives.png" alt="">
              </div>
            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Organization Structure</p>
            </div>
            <div class="body-odd-center">
              <div class="body-odd-left body-odd-left-organization">
                <img src="../assets/img/organizationStructure.png" alt="">
              </div>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">company qualification</div>
            <div class="body-even-center">
              <div class="body-even-company-qualification">
                <div class="company-qualification-row">
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image12.png" alt="">
                    <p>Certification of occupational health and safety management system</p>
                  </div>
                </div>
                <div class="company-qualification-row">
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image13.jpeg" alt="">
                    <p>Business license</p>
                  </div>
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image14.jpeg" alt="">
                    <p>The qualification of the construction labor service enterprise is ungraded</p>
                  </div>

                </div>
                <div class="company-qualification-row">
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image15.png" alt="">
                    <p>Certification of occupational health and safety management system</p>
                  </div>
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image16.png" alt="">
                    <p>Certification of environmental management system</p>
                  </div>
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image17.png" alt="">
                    <p>Certification of quality management system for engineering and construction enterprises</p>
                  </div>
                </div>
                <div class="company-qualification-row">
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image18.png" alt="">
                    <p>Certification of occupational health and safety management system</p>
                  </div>
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image19.png" alt="">
                    <p>Certification of environmental management system</p>
                  </div>
                  <div class="qualification-img-union">
                    <img src="static/img/companyQualification/image20.png" alt="">
                    <p>Certification of quality management system for engineering and construction enterprises</p>
                  </div>
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
  name: "about-weitu",
  components: {
    Banner
  },
  props: {
    casesList: [],
    img: {
      type: String,
      default: require("../assets/img/companyPerformance.png")
    }
  },
  data() {
    return {
      "menuSelected": "company-profile-menu"
    };
  },
  mounted() {
    this.$http.get('static/json/companyCase.json').then(response => {
      this.casesList = response.data;
    })
  },
  methods: {
    selectMenu(event) {
      this.menuSelected = event.target.id;
    }
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

.about-weitu {
  height: 800px;
}

.menu-content-selected {
  font-weight: bold;
}

.about-weitu-menu {
  width: 60%;
  height: 60px;
  background: #E9E9E9;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  position: relative;


  .menu-logo {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-left: 20px;
    line-height: 10px;
  }

  .vertical-divider {
    margin-left: 20px;
    width: 2px;
    height: 50%;
    border-radius: 1px;
    background: #AEABAB;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }

  .menu-content {
    display: flex;
    flex-direction: column;
    justify-content: center;

  }

  .menu-content-detail {
    display: flex;
    justify-content: center;
    padding: 0 30px 3px;
    text-align: center;

    p {
      padding-right: 20px;
      line-height: 30px;
    }

    p:hover {
      cursor: pointer;
      font-weight: bold;
    }


  }

}


.about-weitu-body {
  width: 60%;
  height: 100%;
  margin: 0 auto;

  #construction-management-body {
    width: 100%;
    height: 100%;
  }

  #overview-of-plant-body {
    width: 100%;
    height: 100%;
    background: black;
  }

  #company-profile-body {
    width: 100%;
    height: 100%;
    //background: green;

    .company-case-divider {
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

  .profile-body-even {
    padding: 100px 0;
    margin-bottom: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;

    .body-even-title {
      font-size: 30px;
      font-weight: bold;
      padding-bottom: 50px;
    }

    .body-even-center {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      font-size: 25px;


      .body-even-left {
        width: 50%;
        text-align: left;
        text-indent: 25px;

        p {
          position: relative;
          top: 50%;
          transform: translateY(-50%);
        }
      }

      .body-even-right {
        img {
          width: 100%;
        }
      }

      .body-even-company-qualification {
        display: flex;
        flex-direction: column;
        justify-content: center;

        .company-qualification-row {
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          margin-bottom: 40px;

          .qualification-img-union {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;

            img {
              width: 80%;
            }

            p {
              margin: 20px 0;
            }

          }


        }

      }

    }
  }

  .profile-body-odd {
    padding: 100px 0;
    margin-bottom: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;

    .body-odd-title {
      font-size: 30px;
      font-weight: bold;
      padding-bottom: 50px;
      display: flex;
      flex-direction: row;
      justify-content: flex-end;
    }

    .body-odd-center {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      font-size: 25px;

      .body-odd-left {
        width: 100%;

        img {
          width: 80%;
        }
      }

      .body-odd-left-organization {
        img {
          width: 100%;
        }
      }

      .body-odd-right {
        width: 50%;
        text-align: right;
        text-indent: 25px;

        p {
          position: relative;
          top: 50%;
          transform: translateY(-50%);
        }
      }
    }


    .center-construction-management {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: start;
      font-size: 25px;
    }
  }


}


</style>