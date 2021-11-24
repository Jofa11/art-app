<template>
  <div class="home">
    <header>
      <h1>Creativity Canvas</h1>
      <img alt="art icon" src="../assets/art-icon.png" />
    </header>
    <h3>Welcome to Creativity Canvas!</h3>
    <h5>
      The best site to show off your creativity, unwind after a long day, or
      just doodle. Whatever you are here for, just have fun!
    </h5>
    <router-link to="/art"><button>Get Started!</button></router-link>
  </div>
</template>

<script>
export default {
  name: "Home",
};
</script>

<style scoped>
.home {
  background-image: url("../assets/art-app-background.webp");
  background-repeat: no-repeat;
  background-size: cover;
  padding-bottom: 20%;
}

img {
  width: 7%;
  height: auto;
}

button {
  margin: 1em;
  padding: 1em 2em;
  border-radius: 5px;
  font-size: 1em;
  font-weight: bold;
  background-color: rgb(103, 158, 241);
  box-shadow: 0.2em 0.2em 0.2em rgb(133, 154, 192);
  cursor: pointer;
}
</style>
