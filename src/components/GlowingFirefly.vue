<template>
  <div class="firefly"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.firefly {
  background-color: var(--light);
  border-radius: 50%;
  position: absolute;
  animation: leftright 18s 1 5s cubic-bezier(0.39, 0, 0.63, 1),
    updown 18s 1 5s cubic-bezier(0.39, 0, 0.63, 1),
    glow 18s 1 5s cubic-bezier(0.39, 0, 0.63, 1),
    loop 7s infinite 23s cubic-bezier(0.39, 0, 0.63, 1);
  animation-fill-mode: forwards, forwards;
}

@keyframes glow {
  0% {
    box-shadow: 0 0 10px var(--primary), 0 0 15px var(--primary),
      0 0 30px var(--primary);
  }
  30%,
  78%,
  84% {
    transform: scale(0.9);
    box-shadow: 0 0 5px var(--primary), 0 0 10px var(--primary),
      0 0 15px var(--primary);
  }
  31.5%,
  80% {
    transform: scale(1.2);
    box-shadow: 0 0 20px var(--primary), 0 0 30px var(--primary),
      0 0 50px var(--primary);
  }
  34% {
    transform: scale(1);
    box-shadow: 0 0 10px var(--primary), 0 0 15px var(--primary),
      0 0 30px var(--primary);
  }

  100% {
    box-shadow: 0 0 10px var(--primary), 0 0 15px var(--primary),
      0 0 30px var(--primary);
  }
}

@keyframes leftright {
  0% {
    right: 105%;
    width: 5px;
    height: 5px;
  }
  16.666% {
    right: 80%;
    width: 20px;
    height: 20px;
  }
  34% {
    right: 81%;
    width: 20px;
    height: 20px;
  }
  40% {
    width: 10px;
    height: 10px;
  }
  50% {
    right: 25%;
    width: 18px;
    height: 18px;
  }
  66.666% {
    right: 50%;
    width: 15px;
    height: 15px;
  }
  76% {
    right: 40%;
  }
  83% {
    right: 41%;
    width: 17px;
    height: 17px;
  }
  100% {
    right: 155px;
    width: 15px;
    height: 15px;
  }
}

@keyframes updown {
  0% {
    bottom: 35%;
  }
  25% {
    bottom: 65%;
  }
  50% {
    bottom: 40%;
  }
  70% {
    bottom: 175%;
  }
  82% {
    bottom: 170%;
  }
  100% {
    bottom: 160px;
  }
}

@keyframes loop {
  0%,
  100% {
    bottom: 160px;
    transform: scale(1);

    box-shadow: 0 0 10px var(--primary), 0 0 15px var(--primary),
      0 0 30px var(--primary);
  }
  25% {
    bottom: 169px;
    transform: scale(1.2);

    box-shadow: 0 0 5px var(--primary), 0 0 25px var(--primary),
      0 0 40px var(--primary);
  }
  50% {
    bottom: 164px;
    transform: scale(1.1);

    box-shadow: 0 0 7px var(--primary), 0 0 8px var(--primary),
      0 0 12px var(--primary);
  }
  72% {
    transform: scale(1.3);
  }
  80% {
    bottom: 167px;

    box-shadow: 0 0 3px var(--primary), 0 0 18px var(--primary),
      0 0 35px var(--primary);
  }
}
</style>