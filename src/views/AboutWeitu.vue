<template>
  <div>
    <banner title="ABOUT WEITU" :img="img"></banner>
    <div class="about-weitu">
      <div class="about-weitu-menu">

        <div class="menu-logo">ABOUT WEITU</div>
        <div class="vertical-divider"></div>
        <div class="menu-content">
          <div class="menu-content-detail">
            <p>company profile</p>
            <p>Construction management</p>
            <p>Overview of plant</p>
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

.about-weitu {
  height: 800px;
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

  .vertical-divider{
    margin-left: 20px;
    width: 2px;
    height: 50%;
    border-radius: 1px;
    background: #AEABAB;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }

  .menu-content{
    display: flex;
    flex-direction: column;
    justify-content: center;

  }

  .menu-content-detail{
    display: flex;
    justify-content: center;
    padding: 0  30px 3px;
    text-align: center;

    p{
      padding-right: 20px;
      line-height: 30px;

    }


  }

}


</style>