<template>
  <div class="home">
    <header>
      <img alt="art icon" src="../assets/art-icon.png" />
      <h1>Creativity Canvas</h1>
    </header>
    <h2>Welcome to Creativity Canvas!</h2>
    <h3>
      The best site to show off your creativity, unwind after a long day, or
      just doodle. Whatever you are here for, just have fun!
    </h3>
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
  padding-bottom: 35%;
  color: rgb(162, 39, 211);
}

img {
  width: 7%;
  height: auto;
  padding: 1.6em;
}

header h1 {
  padding-bottom: 5%;
}

h2 {
  font-size: 2.3em;
}

h3 {
  font-size: 1.4em;
  padding: 4%;
}

button {
  margin: 1em;
  padding: 1em 2em;
  border: none;
  border-radius: 5px;
  font-size: 1.2em;
  font-weight: bold;
  background-color: rgb(82, 148, 247);
  box-shadow: 0.2em 0.2em 0.2em rgb(87, 120, 182);
  cursor: pointer;
  font-family: "Finger Paint", cursive;
  color: rgb(251, 236, 252);
  text-shadow: 0.1em 0.1em 0.1em rgb(162, 39, 211);
}
</style>
