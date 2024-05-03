<template>
  <div id="app">
    <el-container>
      <el-header class="header">
        <div class="header-in">
          <div class="logo">
            <img src="./assets/img/weitu-logo.png" alt/>
          </div>
          <el-menu
              :default-active="defaultActive"
              class="el-menu-demo"
              mode="horizontal"
              @select="handleSelect"
              :router="router"
          >
            <el-menu-item index="/">portal</el-menu-item>
            <el-menu-item index="/companyPerformance">company performance</el-menu-item>
            <el-menu-item index="/aboutweitu">about weitu</el-menu-item>
            <el-menu-item index="/case">contact us</el-menu-item>
          </el-menu>
        </div>


      </el-header>
      <el-main>
        <router-view/>
      </el-main>
    </el-container>
    <Footer></Footer>
  </div>
</template>

<script>
import Footer from "./components/Footer";


export default {
  components:{
    Footer
  },
  data() {
    return {
      router: true,
      defaultActive: "/",
      isShow: false,
    };
  },
  methods: {
    handleSelect(key) {
      this.isShow = this.defaultActive != key;
    },
  },
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}

html,
body {
  height: 100%;
}

#app {
  font-family: "Outfit", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.el-header {
  display: flex;
  justify-content: space-between;
  align-content: center;
  width: 100%;
  margin: 0 auto;
  height: 101px !important;
  position: fixed;
  z-index: 10;
  background: #fff;

  .header-in {
    display: flex;
    justify-content: space-between;
    align-content: center;
    width: 60%;
    min-width: 1000px;
    margin: 0 auto;
  }

  .logo {
    width: 130px;
    padding: 40px 0;

    img {
      width: 100%;
      line-height: 26px;
    }
  }
}

.el-main {
  padding: 0 !important;
}

.el-menu--horizontal {
  .el-menu-item {
    height: 0 !important;
    line-height: 0 !important;
  }
}

.el-menu-item {
  height: 0 !important;
  line-height: 0 !important;
  padding: 53px 20px !important;
  font-size: 20px !important;
}

.footer {
  width: 100%;
  height: 216px;
  overflow: hidden;
  background-color: #14679f;

  &-content {
    width: 1240px;
    margin: 0 auto;
    padding-top: 20px;
    display: flex;
    justify-content: space-between;

    .content-nav {
      display: flex;
      justify-content: space-around;

      li {
        display: flex;
        flex-direction: column;
        padding: 0 20px;
        //justify-content: center;
        align-items: flex-start;

        p {
          font-size: 20px;
          color: #d4edff;
          padding: 10px 0;
        }

        span {
          color: #f7f7f7;
          font-weight: 300;
          padding: 5px 0;
        }
      }
    }

    img {
      width: 170px;
      height: 170px;
      padding: 10px;
    }
  }

  .copyright {
    height: 30px;
    background: #125688;

    span {
      color: #fff;
      line-height: 30px;
    }
  }
}
</style>

