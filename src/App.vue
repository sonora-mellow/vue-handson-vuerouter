<template>
  <div id="app">
    <nav>
      <router-link to="/" exact>Home</router-link>
      <router-link to="/product">商品情報</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
import Home from "./views/Home";
import Product from "./views/Product";

export default {
  name: "App",
  components: {
    Home,Product
  }
};
</script>

<style>
.router-link-active { background: #e25193;}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
