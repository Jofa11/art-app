<template>
  <div class="art">
    <router-link to="/"><button id="homeBtn">Home</button></router-link>
    <h1>Creativity Canvas</h1>

    <canvas
      v-on:mousedown="startDrawing()"
      v-on:touchstart="startDrawing()"
      v-on:mouseup="stopDrawing()"
      v-on:touchend="stopDrawing()"
      v-on:mousemove="draw($event)"
      v-on:touchmove="draw($event)"
      id="theCanvas"
      v-bind:width="width"
      v-bind:height="height"
    ></canvas>

    <div id="toolbar" @change="changeHandler">
      <label for="stroke">Color</label>
      <input id="stroke" name="stroke" type="color" />
      <label for="lineWidth">Line Width</label>
      <input id="lineWidth" name="lineWidth" type="number" value="5" /><br />
      <button id="clearBtn" @click="clearCanvas">Clear</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      canvas: null,
      ctx: null,
      drawing: false,
      lineWidth: 5,
      stroke: null,
      width: 350,
      height: 450,
    };
  },
  mounted() {
    window.addEventListener("resize", this.handleResize);
    this.handleResize();
  },

  methods: {
    startDrawing() {
      this.drawing = true;
    },
    handleResize() {
      this.height = window.innerHeight - this.height;
      this.width = window.innerWidth - this.width * 0.6;
      this.$nextTick(() => {
        this.draw();
      });
    },
    stopDrawing() {
      const canvas = document.getElementById("theCanvas");
      const ctx = canvas.getContext("2d");
      this.drawing = false;
      ctx.stroke();
      ctx.beginPath();
    },
    draw(e) {
      const canvas = document.getElementById("theCanvas");
      const ctx = canvas.getContext("2d");

      if (this.drawing && e.type === "touchmove") {
        ctx.lineTo(
          e.touches[0].clientX - canvas.offsetLeft,
          e.touches[0].clientY - canvas.offsetTop
        );
      }

      if (this.drawing) {
        ctx.lineWidth = this.lineWidth;
        ctx.lineCap = "round";
        ctx.lineTo(e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop);
        ctx.lineWidth = this.lineWidth;
        ctx.strokeStyle = this.strokeStyle;
        ctx.stroke();
      }
    },
    changeHandler(e) {
      var canvas = document.getElementById("theCanvas");
      var ctx = canvas.getContext("2d");
      if (e.target.id === "stroke") {
        ctx.strokeStyle = e.target.value;
      }
      if (e.target.id === "lineWidth") {
        this.lineWidth = e.target.value;
      }
    },
    clearCanvas(e) {
      var canvas = document.getElementById("theCanvas");
      var ctx = canvas.getContext("2d");
      if (e.target.id === "clearBtn") {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
      }
    },
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.handleResize);
  },
};
</script>

<style scoped>
#theCanvas {
  border: 15px solid rgb(162, 39, 211);
  background-color: whitesmoke;
  margin-bottom: 1em;
  cursor: url("../assets/paint-brush.png"), auto;
}

button {
  margin: 1em 1em 0 1em;
  padding: 0.5em 1em;
  border-radius: 5px;
  font-size: 1em;
  font-weight: bold;
  cursor: pointer;
  font-family: "Finger Paint", cursive;
  color: rgb(251, 236, 252);
  text-shadow: 0.1em 0.1em 0.1em rgb(162, 39, 211);
}

label {
  padding: 1em;
  font-size: 1.5em;
  font-weight: bold;
  color: rgb(162, 39, 211);
}

input {
  width: 3em;
  border: 2px solid rgb(162, 39, 211);
}

#homeBtn {
  background-color: rgb(173, 147, 233);
  box-shadow: 0.2em 0.2em 0.2em rgb(170, 106, 196);
  border: none;
}

#clearBtn {
  background-color: rgb(235, 85, 185);
  box-shadow: 0.2em 0.2em 0.2em rgb(170, 78, 162);
  border: none;
}

.art {
  background-color: rgb(240, 224, 245);
  background-image: url("../assets/art-app-background.webp");
  width: 100%;
  background-repeat: no-repeat;
  background-size: cover;
  padding-bottom: 6%;
}
</style>
