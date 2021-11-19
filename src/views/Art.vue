<template>
  <div class="art">
    <router-link to="/"><button id="homeBtn">Home</button></router-link>
    <h1>Art App</h1>
    <label for="stroke">Stroke</label>
    <input id="stroke" name="stroke" type="color" />
    <label for="lineWidth">Line Width</label>
    <input id="lineWidth" name="lineWidth" type="number" value="5" />
    <button id="clearBtn">Clear</button>
    <canvas id="theCanvas"></canvas>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawing: false,
      lineWidth: 5,
      startX: null,
      startY: null,
    };
  },
};
</script>

<style scoped>
#theCanvas {
  width: 80%;
  height: auto;
  border: 1em solid black;
}

h1 {
  font-size: 3em;
}

button {
  margin: 1em;
  padding: .5em 1em;
  border-radius: 5px;
  font-size: 1em;
  font-weight: bold;
  cursor: pointer;
}

#homeBtn {
  background-color: rgb(103, 158, 241);
  box-shadow: 0.2em 0.2em 0.2em rgb(133, 154, 192);
}

#clearBtn {
  background-color: rgb(247, 79, 60);
  box-shadow: 0.2em 0.2em 0.2em rgb(228, 158, 156);
}
</style>
