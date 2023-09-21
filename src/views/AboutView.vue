<template>
  <Flipbook class="flipbook" :pages="pages" />
</template>

<script setup>
import Flipbook from "flipbook-vue";
import img1 from "@/assets/book/1.jpg";
import img2 from "@/assets/book/2.jpg";
import img3 from "@/assets/book/3.jpg";
import img4 from "@/assets/book/4.jpg";
import img5 from "@/assets/book/5.jpg";
import img6 from "@/assets/book/6.jpg";

// Массив изображений для модуля Flipbook
const pages = [null, img1, img2, img3, img4, img5, img6];
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}
.flipbook {
  margin: 30px auto;
  width: 80vw;
  height: 80vh;
  .flipbook-container {
    .right::after {
      display: block;
      position: absolute;
      top: 50%;
      right: 0;
      transform: translateY(-100%);
      content: ">";
      font-size: 40px;
      line-height: 50px;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      background: black;
      z-index: 1;
    }
    .left::after {
      display: block;
      position: absolute;
      top: 50%;
      left: 0;
      transform: translateY(-100%);
      content: "<";
      font-size: 40px;
      line-height: 50px;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      background: black;
      z-index: 1;
    }
  }
}
</style>
