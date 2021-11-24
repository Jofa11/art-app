<template>
  <div class="footer">
    <h4>
      This site created by
      <a href="https://joshua-favre-portfolio.herokuapp.com/" class="creator"
        >Joshua Favre</a
      >
    </h4>
    <a
      href="https://www.linkedin.com/in/joshua-favre/"
      target="_blank"
      rel="noreferrer noopener"
      ><img src="../assets/linkedin-icon.png" alt="linkedin icon"
    /></a>
    <a
      href="https://github.com/Jofa11"
      target="_blank"
      rel="noreferrer noopener"
      ><img src="../assets/GitHub-Mark-Light-32px.png" alt="octocat"
    /></a>
    <a
      href="https://twitter.com/FavreJoshua"
      target="_blank"
      rel="noreferrer noopener"
      ><img src="../assets/icons8-twitter-squared-32.png" alt="twitter icon"
    /></a>
  </div>
</template>

<style scoped>
.footer {
  color: whitesmoke;
  position: absolute;
  bottom: 1rem;
  width: 100%;
  height: 12%;
  background-color: rgb(162, 39, 211);
}

.creator {
  color: whitesmoke;
  text-decoration: none;
}

img {
  padding-right: 1em;
}
</style>
