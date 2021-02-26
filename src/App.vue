<template>
  <div id="app">
    <div class="main">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <Header />
          </div>
          <div class="col-8">
            <h1>รายการสินค้า</h1>
            <Casshop />
          </div>
          <div class="col-4"><Cart /></div>
        </div>
      </div>
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";
import Casshop from "./components/Casshop";
import Cart from "./components/Cart";
export default {
  name: "App",
  components: {
    Casshop,
    Footer,
    Header,
    Cart,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>