<template>
  <div class="art">
    <router-link to="/"><button id="homeBtn">Home</button></router-link>
    <h1>Art App</h1>
    <canvas
      v-on:mousedown="startDrawing()"
      v-on:mouseup="stopDrawing()"
      v-on:mousemove="draw($event)"
      id="theCanvas"
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
    };
  },
  // mounted() {
  // //   const canvas = document.getElementById("theCanvas");
  // //   // const ctx = canvas.getContext("2d");

  // //   // Resize canvas
  // //   canvas.height = window.innerHeight - canvas.height;
  // //   canvas.width = window.innerWidth - canvas.width;
  // },
  methods: {
    startDrawing() {
      this.drawing = true;
    },
    stopDrawing() {
      var canvas = document.getElementById("theCanvas");
      var ctx = canvas.getContext("2d");
      this.drawing = false;
      ctx.stroke();
      ctx.beginPath();
    },
    draw(e) {
      var canvas = document.getElementById("theCanvas");
      var ctx = canvas.getContext("2d");
      if (this.drawing) {
        ctx.lineWidth = this.lineWidth;
        ctx.lineCap = "round";
        ctx.lineTo(e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop);
        ctx.stroke();
      }
    },
    // isDrawing(e) {
    //   this.drawing = true;
    //   this.startX = e.clientX;
    //   console.log(e.clientX);
    //   this.startY = e.clientY;
    //   console.log(e.clientY);
    //   // this.draw();
    // },
    // notDrawing() {
    //   const { vueCanvas } = this.$refs;
    //   const ctx = vueCanvas.getContext("2d");
    //   this.drawing = false;
    //   ctx.stroke();
    //   ctx.beginPath();
    // },
    // draw(e) {
    //   // if (e.buttons !== 1) {
    //   //   return;
    //   // }
    //   const { vueCanvas } = this.$refs;
    //   const ctx = vueCanvas.getContext("2d");
    //   this.offsetX = vueCanvas.offsetLeft;
    //   this.offsetY = vueCanvas.offsetTop;
    //   // const { pos } = this;
    //   // if (!this.drawing) {
    //   //   console.log("Not drawing");
    //   //   return;
    //   // }
    //   ctx.beginPath();
    //   ctx.lineWidth = this.lineWidth;
    //   ctx.lineCap = "round";
    //   ctx.moveTo(e.startX, e.startY);
    //   // ctx.moveTo(pos.x, pos.y);
    //   // this.setPosition(e);
    //   ctx.lineTo(e.clientX - this.offsetX, e.clientY);
    //   // ctx.lineTo(pos.x, pos.y);
    //   ctx.stroke();
    // },
    // resize() {
    //   const { vueCanvas } = this.$refs;
    //   const ctx = vueCanvas.getContext("2d");
    //   ctx.canvas.width = window.innerWidth;
    //   ctx.canvas.height = window.innerHeight;
    //   console.log("Resizing");
    // },
    changeHandler(e) {
      var canvas = document.getElementById("theCanvas");
      var ctx = canvas.getContext("2d");
      if (e.target.id === "stroke") {
        ctx.strokeStyle = e.target.value;
        console.log(ctx.strokeStyle);
      }
      if (e.target.id === "lineWidth") {
        this.lineWidth = e.target.value;
        console.log(this.lineWidth);
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
};
</script>

<style scoped>
#theCanvas {
  width: 350px;
  height: 450px;
  border: 12px solid black;
}

h1 {
  font-size: 3em;
}

button {
  margin: 1em;
  padding: 0.5em 1em;
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
  box-shadow: 0.2em 0.2em 0.2em rgb(161, 114, 113);
}
</style>
