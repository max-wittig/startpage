<template>
  <div id="app">
    <navbar />
    <Grid />
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "app",
  components: {
    Grid,
    Navbar
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
