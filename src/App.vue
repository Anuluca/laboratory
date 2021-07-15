<template>
  <div id="nav">
    <div class="title">路卡的实验室</div>
    <router-link to="/">
      <div class="router">Home</div>
    </router-link>
    <router-link to="/pokeWatch">
      <div class="router">宝可手表</div>
    </router-link>
    <router-link to="/waterfall">
      <div class="router">简易瀑布流</div>
    </router-link>
  </div>
  <div class="main-page">
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  width: 300px;
  height: calc(100vh - 60px);
  margin: 0;
  float: left;
  border-radius: 9px;
  box-shadow: 0px 2px 8px 0px #d7d7d7;
  border: 1px solid #ebebeb;
  margin-left: 15px;
  background-color: #f6f6f6;
  margin-top: 15px;
  .title {
    font-size: 30px;
    font-weight: bold;
    text-align: center;
    margin-top: 30px;
    margin-bottom: 50px;
  }
  a {
    line-height: 50px;
    text-align:center;
    font-weight: bold;
    font-size: 22px;
    text-decoration: none;
    color: #2c3e50;
    .router {
      width: 200px;
      height: 50px;
      margin: 20px 50px;
      border-radius: 5px;
    }
    &.router-link-exact-active {
      color: white;
      .router {
        background-color: #f33d45;
      }
    }
  }
}
.main-page {
  width: calc(100% - 336px);
  height: calc(100vh - 62px);
  float: right;
  overflow:scroll;
  margin-top:20px
}
</style>
