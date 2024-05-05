<template>
  <div id="app">
    <el-container>
      <el-header class="header">
        <div class="header-in">
          <div class="logo">
            <img src="./assets/img/weitu-logo.png" alt/>
          </div>
          <el-menu v-if="isWideScreen" :default-active="defaultActive" mode="horizontal" @select="handleSelect"
                   :router="router" class="horizontal-menu">
            <el-menu-item index="/">portal</el-menu-item>
            <el-menu-item index="/companyPerformance">company performance</el-menu-item>
            <el-menu-item index="/aboutweitu">about weitu</el-menu-item>
            <el-menu-item index="/contactus">contact us</el-menu-item>
          </el-menu>
          <el-menu v-else :default-active="defaultActive" mode="vertical" :collapse=false @select="handleSelect"
                   :router="router" class="vertical-menu">
            <el-submenu index="">
              <template slot="title">
                <i class="el-icon-menu"></i>
              </template>
              <el-menu-item index="/">portal</el-menu-item>
              <el-menu-item index="/companyPerformance">company performance</el-menu-item>
              <el-menu-item index="/aboutweitu">about weitu</el-menu-item>
              <el-menu-item index="/contactus">contact us</el-menu-item>
            </el-submenu>
          </el-menu>
        </div>
      </el-header>


      <el-main>
        <router-view/>
      </el-main>
    </el-container>
  </div>
</template>

<script>
import Footer from "./components/Footer";

export default {
  components: {
    Footer,
  },
  data() {
    return {
      router: true,
      defaultActive: "/",
      isShow: false,
      isWideScreen:true,
    };
  },
  created() {
    this.$nextTick(() => {
      const screenWide = window.innerWidth || document.documentElement.clientWidth;
      this.isWideScreen = screenWide >= 1000;
    })
  },
  mounted() {
    window.onresize = () => {
      const screenWide = window.innerWidth || document.documentElement.clientWidth;
      this.isWideScreen = screenWide >= 1000;
    }
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
}

.el-header {
  display: flex;
  justify-content: space-between;
  align-content: center;
  width: 100%;
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
    margin-inline: auto;
    height: 100%;
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

.el-menu.horizontal-menu {
  height: 100% !important;
  display: flex;
  align-items: center;
}


.el-menu.vertical-menu {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-right: none;
  position: fixed;
  right: 0;
  top: 25px;

  .el-submenu__title:hover{
    background: white !important;
  }

  .el-submenu__title{
    padding: 0 40px !important;
    i {
      color: black;
    }

    .el-icon-menu{
      margin-right: 10px;
    }

    .el-submenu__icon-arrow {
      //display: none;
      color: black;
    }
  }

  .el-menu-item{
    color: #909399;
  }

  .el-menu-item.is-active {
    color: #303133;
    background: white !important;
  }


  .is-active.is-opened {
    //background-color: #303133 !important;
  }


  //position: absolute;
  //float: right;
  //right: 0;
  //margin-top: 150px;
  .el-submenu {
    top: 0;
  }

  .el-submenu.is-active{
    .el-submenu__title{
      border-bottom-color: black !important;
    }
  }
}

.is-active {
  border: unset !important;
  background: white !important;
}

.el-menu-item {
  font-size: 20px !important;
  border: unset !important;
}

.el-menu-item.is-active {
}

//@media (max-width: 992px) {
//  .el-header {
//    display: none;
//  }
//}
//
//.el-menu-vertical-right {
//  width: 200px;
//  min-height: 100%;
//  position: fixed;
//  left: 0;
//  top: 64px;
//  bottom: 0;
//}
</style>

