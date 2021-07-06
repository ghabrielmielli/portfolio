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
    left: -5%;
    width: 5px;
    height: 5px;
  }
  16.666% {
    left: 20%;
    width: 20px;
    height: 20px;
  }
  34% {
    left: 19%;
    width: 20px;
    height: 20px;
  }
  40% {
    width: 10px;
    height: 10px;
  }
  50% {
    left: 75%;
    width: 18px;
    height: 18px;
  }
  66.666% {
    left: 50%;
    width: 15px;
    height: 15px;
  }
  76% {
    left: 60%;
  }
  83% {
    left: 59%;
    width: 17px;
    height: 17px;
  }
  100% {
    left: 84%;
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
    bottom: 43%;
  }
}

@keyframes loop {
  0%,
  100% {
    bottom: 44%;
    transform: scale(1);

    box-shadow: 0 0 10px var(--primary), 0 0 15px var(--primary),
      0 0 30px var(--primary);
  }
  25% {
    bottom: 52%;
    transform: scale(1.2);

    box-shadow: 0 0 5px var(--primary), 0 0 25px var(--primary),
      0 0 40px var(--primary);
  }
  50% {
    bottom: 46%;
    transform: scale(1.1);

    box-shadow: 0 0 7px var(--primary), 0 0 8px var(--primary),
      0 0 12px var(--primary);
  }
  72% {
    transform: scale(1.3);
  }
  80% {
    bottom: 49%;

    box-shadow: 0 0 3px var(--primary), 0 0 18px var(--primary),
      0 0 35px var(--primary);
  }
}
</style>