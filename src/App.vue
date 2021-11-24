<template>
  <div>
    <Footer />
  </div>
  <router-view />
</template>

<script>
import Footer from "./components/Footer.vue";

export default {
  components: {
    Footer,
  },
};
</script>

<style>
html,
body {
  width: 100%;
  height: 100%;
  margin: 0px;
  padding: 0px;
  overflow-x: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1 {
  font-family: "Finger Paint", cursive;
  font-size: 3.5em;
  font-weight: 900;
  color: rgb(251, 236, 252);
  text-shadow: 0.1em 0.1em 0.1em rgb(162, 39, 211);
  margin: 0.2em;
}
</style>
