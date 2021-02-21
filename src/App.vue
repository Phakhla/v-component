<template>
  <div id="app">
     
    <b-navbar
      toggleable="lg"
      type="dark"
      variant="warning"
      class="navbar-horizontal"
    >
    <h1>Cassshop</h1>
    </b-navbar>
    
    <router-view />
    
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
</style>