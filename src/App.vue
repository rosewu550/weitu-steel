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

          <el-dropdown @command="handleCommand" v-else>
            <span>
              <i class="el-icon-menu el-icon--right"></i>
            </span>
            <el-dropdown-menu>
              <el-dropdown-item command="/">portal</el-dropdown-item>
              <el-dropdown-item command="/companyPerformance">company performance</el-dropdown-item>
              <el-dropdown-item command="/aboutweitu">about weitu</el-dropdown-item>
              <el-dropdown-item command="/contactus">contact us</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </el-header>
      <el-main>
        <router-view/>
      </el-main>
<!--      <Footer></Footer>-->
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
      isWideScreen: true,
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
    handleCommand(command) {
      this.$router.push({ path: command });
    }
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


.el-icon-menu {
  font-size: 35px;
  color: black;
}

.el-dropdown{
  display: flex !important;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-right: none;
  position: fixed !important;
  right: 20px;
  top: 35px;
}

.el-dropdown-menu {
  .el-dropdown-menu__item {
    font-size: 20px !important;
    font-family: "Outfit", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #909399;
  }
}

.el-dropdown-menu__item:focus, .el-dropdown-menu__item:not(.is-disabled):hover{
  background-color: rgba(211, 211, 211, 0.28) !important;
  color:black !important;
}

.el-menu.el-menu--horizontal{
  border-bottom: none !important;
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

  .el-submenu__title:hover {
    background: white !important;
  }

  .el-submenu__title {
    padding: 0 40px !important;

    i {
      color: black;
    }

    .el-icon-menu {
      margin-right: 10px;
    }

    .el-submenu__icon-arrow {
      //display: none;
      color: black;
    }
  }

  .el-menu-item {
    color: #909399;
  }

  .el-menu-item.is-active {
    color: #303133;
    background: white !important;
  }


  .is-active.is-opened {
    //background-color: #303133 !important;
  }

  .el-submenu {
    top: 0;
  }

  .el-submenu.is-active {
    .el-submenu__title {
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
</style>

