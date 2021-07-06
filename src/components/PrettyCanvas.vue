<template >
  <div class="mainDiv">
    <canvas id="c"> </canvas>
    <slot></slot>
  </div>
</template>
<script>
export default {
  data() {
    return {
      c: null,
      cWidth: innerWidth,
      cHeigth: innerHeight,
      cRestrictFat: 300, //a higher value than 0 makes the ball able to go off the screen.
      cColor: "#0C1115",

      ball: {
        x: innerWidth / 2,
        y: innerHeight / 2,
        radius: innerHeight / 2,

        //moon-like properties
        alpha: 0.05, //color alpha
        isWaningMoon: false,
        moonCycleSpeed: 0.25,

        velocity: {
          x: -1,
          y: 1,
          offset: {
            // the velocity for bounce back. its the base value + a random value between 0 and the offset value.
            x: 0.5,
            y: 0.7,
            baseX: 0.2,
            baseY: 0.3,
          },
        },
        gravity: 0.002,
      },
    };
  },
  computed: {
    ballColor: function () {
      let color = `rgba(190, 47, 41, ${this.ball.alpha})`;
      return color;
    },
  },
  mounted() {
    var c = document.getElementById("c");
    c.width = this.cWidth;
    c.height = this.cHeigth;
    var ctx = c.getContext("2d");
    this.c = ctx;
    this.animate();

    addEventListener("resize", () => {
      this.cWidth = c.width = innerWidth;
      this.cHeigth = c.height = innerHeight;
      this.ball.radius = innerHeight / 2;
    });
  },
  methods: {
    draw() {
      this.c.beginPath();
      this.c.arc(
        this.ball.x,
        this.ball.y,
        this.ball.radius,
        0,
        Math.PI * 2,
        false
      );
      this.c.fillStyle = this.ballColor;
      this.c.fill();
      this.c.closePath();
    },
    update() {
      this.updateBallAttributes();
      this.restrictToCanvas();

      this.paintBackground();
      this.draw();
    },
    updateBallAttributes() {
      this.ball.x += this.ball.velocity.x;
      this.ball.y += this.ball.velocity.y;

      //Makes the ball bounce when hit the ground
      if (this.isOutOfCorner("bottom")) {
        this.ball.velocity.y =
          ((Math.random() * 100) % this.ball.velocity.offset.y) +
          this.ball.velocity.offset.baseY;
      } else {
        this.ball.velocity.y += this.ball.gravity;
      }

      this.changeMoonPhase();
    },
    paintBackground() {
      this.c.fillStyle = this.cColor;
      this.c.fillRect(0, 0, this.cWidth, this.cHeigth);
    },
    animate() {
      requestAnimationFrame(this.animate);
      this.c.clearRect(0, 0, this.cWidth, this.cHeigth);
      this.update();
    },
    restrictToCanvas() {
      //Swap the velocity on colision
      if (this.isOutOfCorner("left") || this.isOutOfCorner("right")) {
        this.ball.velocity.x =
          ((Math.random() * 100) % this.ball.velocity.offset.x) +
          this.ball.velocity.offset.baseX;
        if (this.isOutOfCorner("right")) this.ball.velocity.x *= -1;
      }

      if (this.isOutOfCorner("top") || this.isOutOfCorner("bottom"))
        this.ball.velocity.y *= -1;

      //Debug 'eternal colision'
      let corners = ["top", "bottom", "right", "left"];
      corners.forEach((corner) => {
        if (this.isOutOfCorner(corner)) this.adjustToCorner(corner);
      });
    },
    isOutOfCorner(side) {
      switch (side) {
        case "top":
          return this.ball.y - this.ball.radius < 0 - this.cRestrictFat;
        case "bottom":
          return (
            this.ball.y + this.ball.radius > this.cHeigth + this.cRestrictFat
          );
        case "left":
          return this.ball.x - this.ball.radius < 0 - this.cRestrictFat;
        case "right":
          return (
            this.ball.x + this.ball.radius > this.cWidth + this.cRestrictFat
          );
      }
    },
    adjustToCorner(side) {
      switch (side) {
        case "top":
          this.ball.y = this.ball.radius - this.cRestrictFat;
          break;
        case "bottom":
          this.ball.y = this.cHeigth - this.ball.radius + this.cRestrictFat;
          break;
        case "left":
          this.ball.x = this.ball.radius - this.cRestrictFat;
          break;
        case "right":
          this.ball.x = this.cWidth - this.ball.radius + this.cRestrictFat;
          break;
      }
    },
    changeMoonPhase() {
      if (this.ball.isWaningMoon) {
        if (this.ball.alpha > 0.4) {
          this.ball.alpha -= 0.001 * this.ball.moonCycleSpeed;
        } else {
          this.ball.isWaningMoon = false;
        }
      } else {
        if (this.ball.alpha < 1) {
          this.ball.alpha += 0.001 * this.ball.moonCycleSpeed;
        } else {
          this.ball.isWaningMoon = true;
        }
      }
    },
  },
};
</script>
<style scoped>
#c {
  position: fixed;
  z-index: -1;
}
.mainDiv {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: baseline;
}
</style>