<template>
  <div class="home">
    <h1>Art App</h1>
    <img alt="art icon" src="../assets/art-icon.png" />
    <h3>Welcome to Art App!</h3>
    <h5>The best site to show off your creativity, unwind after a long day, or just doodle. Whatever you are here for, just have fun!</h5>
    <router-link to="/art"><button>Get Started!</button></router-link>
  </div>
</template>

<script>
export default {
  name: "Home",
  
};
</script>
