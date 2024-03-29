<template>
  <PageContent>
    <MainTitle />
    <router-view />
  </PageContent>
  <video v-if="isDesktop" autoplay muted loop id="myVideo">
    <source src="@/assets/desktop.mp4" type="video/mp4" />
  </video>
  <video v-else autoplay muted playsinline loop preload="metadata" id="myVideo">
    <source src="@/assets/mobile.mp4" type="video/mp4" />
  </video>
  <div class="bubble bubble--1"></div>
  <div class="bubble bubble--2"></div>
  <div class="bubble bubble--3"></div>
  <div class="bubble bubble--4"></div>
  <div class="bubble bubble--5"></div>
  <div class="bubble bubble--6"></div>
  <div class="bubble bubble--7"></div>
  <div class="bubble bubble--8"></div>
  <div class="bubble bubble--9"></div>
  <div class="bubble bubble--10"></div>
  <div class="bubble bubble--11"></div>
  <div class="bubble bubble--12"></div>
</template>

<script lang="ts" setup>
import { onMounted, ref } from "vue";
import MainTitle from "@/components/MainTitle.vue";
import PageContent from "@/containers/PageContent.vue";

let isDesktop = ref(false);

onMounted(() => {
  const handleResize = () => {
    isDesktop.value = window.innerWidth >= 600;
  };

  handleResize(); // Set initial value

  window.addEventListener("resize", handleResize);
});
</script>

<style lang="scss">
@import "@/styles/variables.scss";

#app {
  position: relative;
  overflow: hidden;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
html,
body {
  margin: 0;
  padding: 0;
  scrollbar-width: none;
  -ms-overflow-style: none;
  ::-webkit-scrollbar {
    display: none;
  }
}
body {
  background: linear-gradient(-45deg, #660b0b, #240808, #5c4646, #000000);
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  video {
    position: absolute;
    left: 0;
    top: 0;
    opacity: 0.5;
    min-width: 100%;
    min-height: 100%;
    z-index: -1;
    @media screen and (max-width: 600px) {
      top: -30%;
    }
    @media screen and (max-width: 500px) {
      top: -15%;
    }
  }
}

.bubble {
  z-index: 0;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  position: absolute;
  background-color: white;
  bottom: -30px;
  opacity: 0.2;
  background-size: cover;
  animation: bubble 15s ease-in-out infinite,
    sideWays 4s ease-in-out infinite alternate;
}

.bubble--1 {
  left: 10%;
  animation-delay: 0.5s;
  animation-duration: 16s;
  opacity: 0.2;
}

.bubble--2 {
  width: 15px;
  height: 15px;
  left: 40%;
  animation-delay: 1s;
  animation-duration: 10s;
  opacity: 0.1;
}

.bubble--3 {
  width: 10px;
  height: 10px;
  left: 30%;
  animation-delay: 5s;
  animation-duration: 20s;
  opacity: 0.3;
}

.bubble--4 {
  width: 25px;
  height: 25px;
  left: 40%;
  animation-delay: 8s;
  animation-duration: 17s;
  opacity: 0.2;
}

.bubble--5 {
  width: 30px;
  height: 30px;
  left: 60%;
  animation-delay: 10s;
  animation-duration: 15s;
  opacity: 0.1;
}

.bubble--6 {
  width: 10px;
  height: 10px;
  left: 80%;
  animation-delay: 3s;
  animation-duration: 30s;
  opacity: 0.4;
}

.bubble--7 {
  width: 15px;
  height: 15px;
  left: 90%;
  animation-delay: -7s;
  animation-duration: 25s;
  opacity: 0.3;
}

.bubble--9 {
  width: 20px;
  height: 20px;
  left: 50%;
  bottom: 30px;
  animation-delay: -5s;
  animation-duration: 19s;
  opacity: 0.2;
}

.bubble--10 {
  width: 40px;
  height: 40px;
  left: 30%;
  bottom: 30px;
  animation-delay: -21s;
  animation-duration: 16s;
  opacity: 0.3;
}

.bubble--11 {
  width: 30px;
  height: 30px;
  left: 60%;
  bottom: 30px;
  animation-delay: -13.75s;
  animation-duration: 20s;
  opacity: 0.3;
}

.bubble--11 {
  width: 25px;
  height: 25px;
  left: 90%;
  bottom: 30px;
  animation-delay: -10.5s;
  animation-duration: 19s;
  opacity: 0.3;
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes bubble {
  0% {
    transform: translateY(0%);
    opacity: 0.06;
  }
  100% {
    transform: translateY(-120vh);
  }
}

@keyframes sideWays {
  0% {
    margin-left: 0px;
  }
  100% {
    margin-left: 200px;
  }
}

@keyframes animateSprite {
  0% {
    background-position: -600px; /* Starting position moving left sprite */
  }
  20% {
    background-position: 0px; /* Straight on sprite */
  }
  25% {
    background-position: -200px; /* Moving up sprite */
  }
  35% {
    background-position: -400px; /* Moving right sprite */
  }
  40% {
    background-position: -400px;
  }
  50% {
    background-position: -200px; /* Moving up sprite */
  }
  60% {
    background-position: -0px; /* Straight on sprite */
  }
  67% {
    background-position: -600px; /* Moving up sprite */
  }

  100% {
    background-position: -600px;
  }
}

@keyframes swim {
  0% {
    transform: translate(0, 0); /* Starting position */
  }
  20% {
    transform: translate(
      calc(-50vw - 100px),
      0
    ); /* Animate to center of screen */
  }
  25% {
    transform: translate(
      calc(-50vw - 100px),
      0
    ); /* Stay at the center for 1 second */
  }
  35% {
    transform: translate(
      calc(-50vw - 100px),
      -20vh
    ); /* Animate up for 2 seconds */
  }
  50% {
    transform: translate(-25vw, 15vh); /* Animate bottom right for 3 seconds */
  }
  60% {
    transform: translate(-25vw, -20vh); /* Animate up at right of the screen */
  }
  67% {
    transform: translate(-25vw, -20vh);
  }

  100% {
    transform: translate(
      calc(-100vw - 300px),
      0
    ); /* Animate past left past the screen */
  }
}
</style>
