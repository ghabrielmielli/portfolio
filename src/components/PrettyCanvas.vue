<template >
  <div>
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
      cColor: "#2B3240",

      ball: {
        x: 80,
        y: 80,
        radius: 300,
        color: "#8596A6",

        mass: 0.2,

        velocity: {
          x: 1,
          y: (Math.random() - 0.5) * 10,
        },
        gravity: 0.03,
      },
    };
  },
  mounted() {
    var c = document.getElementById("c");
    c.width = this.cWidth;
    c.height = this.cHeigth;
    var ctx = c.getContext("2d");
    this.c = ctx;
    this.animate();
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
      this.c.fillStyle = this.ball.color;
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

      //Impulsiona a bola ao tocar no chão
      if (this.ball.y + this.ball.radius >= this.cHeigth) {
        this.ball.velocity.y = ((Math.random() * 10) % 3) + 2;
      } else {
        this.ball.velocity.y += this.ball.gravity;
      }
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
      if (
        this.ball.x - this.ball.radius < 0 ||
        this.ball.x + this.ball.radius > this.cWidth
      ) {
        this.ball.velocity.x = -this.ball.velocity.x;
      }
      if (
        this.ball.y - this.ball.radius < 0 ||
        this.ball.y + this.ball.radius > this.cHeigth
      ) {
        this.ball.velocity.y = -this.ball.velocity.y;
      }

      //Debug 'eternal colision'
      if (this.ball.x - this.ball.radius < 0) {
        this.ball.x = this.ball.radius;
      } else if (this.ball.x + this.ball.radius > this.cWidth) {
        this.ball.x = this.cWidth - this.ball.radius;
      }

      if (this.ball.y - this.ball.radius < 0) {
        this.ball.y = this.ball.radius;
      } else if (this.ball.y + this.ball.radius > this.cHeigth) {
        this.ball.y = this.cHeigth - this.ball.radius;
      }
    },
  },
};
</script>
<style >
#c {
  position: fixed;
  z-index: -1;
}
</style>