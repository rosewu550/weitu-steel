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
          <div class="profile-body-even">
            <div class="body-even-title">Occupational health and environmental protection management system</div>
            <div class="body-even-center">
              <div class="center-construction-management">
                <p>I. General objectives of occupational health and safety</p>
                <p>II. Environmental protection objectives</p>
                <p>III. Environmental management system</p>
                <p>IV. Environmental management organization</p>
                <p>V. Environmental management responsibilities</p>
                <p>Ⅵ. Environmental management process</p>
                <p>VII. Determination of the list of significant environmental factors</p>
                <p>VIII. Environmental management rules and regulations</p>
                <p>IX. Environmental protection measures</p>
                <p>X. Measures for controlling dust, noise, moisture, and water pollution</p>
              </div>


            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Hazard analysis and evaluation</p>
            </div>
            <div class="center-construction-management">
              <p>Considering the unique characteristics of each project and the diverse construction environments,
                conduct a comprehensive analysis of activities across the entire site. This involves a meticulous risk
                assessment for each step of the project, identifying potential safety hazards associated with each
                operational activity. Delve into the types of hazards and potential safety accidents stemming from each
                hazardous source, and subsequently formulate corresponding control measures.</p>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">PPE</div>
            <div class="body-even-center">
              <div class="center-construction-management">
                <p>Key factors taken into account during the analysis and evaluation: Psychological factors, material
                  and equipment considerations, environmental and natural disaster factors, hazardous material and
                  chemical elements, as well as human error factors.</p>
                <p>Activities involving primary sources of danger: Working at heights, electrical work, hoisting
                  operations, welding and cutting activities, equipment installation, and the operation of construction
                  machinery.</p>
              </div>


            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Safety penalties and safety meetings</p>
            </div>
            <div class="center-construction-management">
              <p>Implement a safety penalty system on-site. Individuals found in violation of safety regulations will be
                subject to penalties, and comprehensive records of these incidents will be maintained. Any employee
                subject to three penalties on-site will be directed to leave the premises. Conversely, commendations and
                necessary rewards are bestowed upon individuals who consistently adhere to and excel in complying with
                safety regulations in their daily activities.</p>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">Education and training</div>
            <div class="body-even-center">
              <div class="center-construction-management">
                <p>Educational methods encompass reviewing rules and regulations, viewing instructional videos, and
                  completing written assessments.</p>
                <p>Each employee is required to undergo three levels of education, with the primary content focusing
                  on:</p>
                <p>1.Basic knowledge of safety, laws and regulations</p>
                <p>2.Education on site regulations and discipline</p>
                <p>3.Post safety operation, safety system education</p>
                <p>Provide safety education to employees in accordance with the specific regulations of the project and
                  the company.</p>
                <p>Present videos depicting accidents to help employees directly see the critical importance of safety.
                  Subsequently, conduct analyses and explanations of the incidents to reinforce the understanding of
                  safety principles.</p>
                <p>After safety education, each employee must undergo a written assessment to gauge their mastery of
                  safety knowledge. Only those scoring 90 points or higher in the assessment are permitted to engage in
                  field operations.</p>
                <p>Upon entering the site, employees will receive safety technology briefings based on the labor
                  category and specific operation.</p>

              </div>


            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Quality control target</p>
            </div>
            <div class="center-construction-management">
              <p>The sub-parts of the project must achieve a 100% passing rate, meeting the specified requirements of
                the owner.
                To ensure the attainment of the project's quality objectives, we have implemented a comprehensive
                quality management system along with effective management methods and measures.
                To accomplish our management objectives, our company has instituted a structure wherein a project
                manager oversees the project, a designated technical lead manages project-related technical aspects, and
                a project quality officer ensures specific implementation. Additionally, the company's technology,
                quality, materials, equipment, and other relevant departments contribute to the oversight and inspection
                of the quality assurance system. This meticulous organizational framework is established to guarantee a
                reliable and robust system, ultimately ensuring the quality of the project. The primary emphasis is on
                the execution of our quality management system and quality inspection program, targeting the following
                five key areas:
              </p>
              <p>1.Quality of work on important projects</p>
              <p>2.General engineering quality</p>
              <p>3.Quality control of materials before and after installation</p>
              <p>4.System and equipment testing</p>
              <p>5.Quality of documentation control</p>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">Progress control target</div>
            <div class="body-even-center">
              <div class="center-construction-management">
                <p>Ensure the timely completion of the contracted work within the specified</p>
                <p>contract period.</p>
              </div>
            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Quality control target</p>
            </div>
            <div class="center-construction-management">
              <p>The sub-parts of the project must achieve a 100% passing rate, meeting the specified requirements of
                the owner.
                To ensure the attainment of the project's quality objectives, we have implemented a comprehensive
                quality management system along with effective management methods and measures.
                To accomplish our management objectives, our company has instituted a structure wherein a project
                manager oversees the project, a designated technical lead manages project-related technical aspects, and
                a project quality officer ensures specific implementation. Additionally, the company's technology,
                quality, materials, equipment, and other relevant departments contribute to the oversight and inspection
                of the quality assurance system. This meticulous organizational framework is established to guarantee a
                reliable and robust system, ultimately ensuring the quality of the project. The primary emphasis is on
                the execution of our quality management system and quality inspection program, targeting the following
                five key areas:
              </p>
              <p>1.Quality of work on important projects</p>
              <p>2.General engineering quality</p>
              <p>3.Quality control of materials before and after installation</p>
              <p>4.System and equipment testing</p>
              <p>5.Quality of documentation control</p>
            </div>
          </div>
          <div class="profile-body-even">
            <div class="body-even-title">Emergency handling procedure</div>
            <div class="body-even-center even-center-emergency">
              <img src="static/img/construction/EmergencyHandlingProcedure.png" alt="">
            </div>
          </div>
          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Catch-up plan process</p>
            </div>
            <div class="body-odd-center odd-center-catchUp">
              <img src="static/img/construction/CatchUpPlanProcess.png" alt="">
            </div>
          </div>
        </div>


        <div v-else-if="menuSelected === 'overview-of-plant-menu'" id="overview-of-plant-body">
          <div class="profile-body-even">
            <div class="body-even-title">Plant introduction</div>
            <div class="body-even-center">
              <div class="body-even-left">
                <p>Shanghai Weitu Steel Structure Engineering Co., Ltd. is the proprietor of both Langxi Steel Structure
                  Processing Plant and Wuxi Qunli Cooperative Steel Structure Processing Plant.
                  Langxi Steel Structure Processing Plant, with an area of approximately 2,000 square meters, primarily
                  focuses on processing small components and precision-required spare parts. The annual steel structure
                  output from this facility is around 1,000 tons.
                  Wuxi Qunli Steel Structure Processing Plant boasts a substantial plant building area of approximately
                  40,000 square meters, producing an annual output of around 20,000 tons of steel structure.
                </p>
              </div>
              <div class="body-even-right even-right-plant">
                <img src="static/img/overview/image24.jpg" alt="">
              </div>
            </div>
          </div>

          <div class="profile-body-odd">
            <div class="body-odd-title">
              <p>Plant overview--Langxi Plant</p>
            </div>
            <div class="body-odd-center center-plant-overview">
              <div class="plant-overview-grid-first">
                <img src="static/img/overview/image28.jpeg" alt="">
                <img src="static/img/overview/image26.jpeg" alt="">
                <img src="static/img/overview/image27.jpeg" alt="">
                <img src="static/img/overview/image29.png" alt="">
              </div>
              <div class="plant-overview-grid-second">
                <img src="static/img/overview/image25.jpeg" alt="">
                <img src="static/img/overview/image30.png" alt="">
                <img src="static/img/overview/image31.jpg" alt="">
              </div>
            </div>
          </div>


          <div class="profile-body-even">
            <div class="body-even-title">Plant overview--Wuxi Plant</div>
            <div class="body-even-center center-plant-overview">
              <div class="plant-overview-grid-first">
                <img src="static/img/overview/image35.jpeg" alt="">
                <img src="static/img/overview/image33.jpeg" alt="">
                <img src="static/img/overview/image34.jpeg" alt="">
                <img src="static/img/overview/image36.png" alt="">
              </div>
              <div class="plant-overview-grid-second">
                <img src="static/img/overview/image32.jpeg" alt="">
                <img src="static/img/overview/image37.png" alt="">
                <img src="static/img/overview/image38.jpeg" alt="">
              </div>
            </div>
          </div>

        </div>


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

      .even-right-plant {
        width: 500px;
      }

    }

    .even-center-emergency {
      img {
        width: 100%;
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
      text-align: center;
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

    .odd-center-catchUp {
      img {
        width: 100%;
      }
    }
  }
}


.center-plant-overview {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  overflow: hidden;

  .plant-overview-grid-first {
    display: grid;
    grid: auto-flow dense / 1fr 1fr;
    column-gap: 10px;
    row-gap: 10px;
    margin-right: 20px;
    width: 100%;
    height: 100%;


    img {
      width: 100%;
      height: 300px;
    }
  }

  .plant-overview-grid-second {
    display: grid;
    grid: auto-flow dense / 1fr  1fr;
    column-gap: 10px;
    row-gap: 10px;
    width: 100%;



    img {
      width: 100%;
      height: 300px;
    }
  }
}


</style>