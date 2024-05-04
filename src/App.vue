<template>
  <div id="app">
    <el-container>
      <el-header class="header">
        <div class="header-in">
          <div class="logo">
            <img src="./assets/img/weitu-logo.png" alt />
          </div>
          <el-menu :default-active="defaultActive" mode="horizontal" @select="handleSelect" :router="router">
            <el-menu-item index="/">portal</el-menu-item>
            <el-menu-item index="/companyPerformance">company performance</el-menu-item>
            <el-menu-item index="/aboutweitu">about weitu</el-menu-item>
            <el-menu-item index="/contactus">contact us</el-menu-item>
          </el-menu>
        </div>
      </el-header>
      <el-main>
        <router-view />
      </el-main>
    </el-container>
    <Footer></Footer>
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
.el-menu {
  height: 100% !important;
  display: flex;
  align-items: center;
}

.is-active {
  border: unset !important;
}

.el-menu-item {
  font-size: 20px !important;
  border: unset !important;
}

.el-menu-item.is-active {
}
</style>

