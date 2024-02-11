<template>
  <p class="desc">
    Листайте книжку используя кнопки
    <br />
    или переворачивая страницы вручную!
  </p>
  <Flipbook
    class="flipbook"
    :zooms="[1]"
    :pages="pages"
    v-slot="flipbook"
    ref="flipbook"
  >
    <div class="action-bar">
      <div
        class="btn left"
        :class="{ disabled: !flipbook.canFlipLeft }"
        @click="flipbook.flipLeft"
      ></div>
      <span class="page-num">
        {{ flipbook.page }} из {{ flipbook.numPages }}
      </span>
      <div
        class="btn right"
        :class="{ disabled: !flipbook.canFlipRight }"
        @click="flipbook.flipRight"
      ></div>
    </div>
    <Back />
  </Flipbook>
</template>

<script setup>
import Flipbook from "flipbook-vue";
import Back from "@/components/BackButton.vue";
import img1 from "@/assets/book/1.jpg";
import img2 from "@/assets/book/2.jpg";
import img3 from "@/assets/book/3.jpg";
import img4 from "@/assets/book/4.jpg";
import img5 from "@/assets/book/5.jpg";
import img6 from "@/assets/book/6.jpg";
import img7 from "@/assets/book/7.jpg";
import img8 from "@/assets/book/8.jpg";
import img9 from "@/assets/book/9.jpg";
import img10 from "@/assets/book/10.jpg";
import img11 from "@/assets/book/11.jpg";
import img12 from "@/assets/book/12.jpg";
import img13 from "@/assets/book/13.jpg";
import img14 from "@/assets/book/14.jpg";
import img15 from "@/assets/book/15.jpg";
import img16 from "@/assets/book/16.jpg";
import img17 from "@/assets/book/17.jpg";
import img18 from "@/assets/book/18.jpg";

// Массив изображений для модуля Flipbook
const pages = [
  null,
  img1,
  img2,
  img3,
  img4,
  img5,
  img6,
  img7,
  img8,
  img9,
  img10,
  img11,
  img12,
  img13,
  img14,
  img15,
  img16,
  img17,
  img18,
];
</script>

<style lang="scss">
@import "@/styles/variables.scss";
.desc {
  font-size: 24px;
  color: $white-1;
}
.flipbook {
  position: relative;
  z-index: 1;
  margin: 0px auto;
  display: flex;
  flex-direction: column-reverse;
  .btn {
    width: 20px;
    height: 20px;
    background-color: aquamarine;
    border-radius: 50%;
  }
  .action-bar {
    width: 100%;
    height: 30px;
    padding: 10px 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .action-bar .btn {
    font-size: 30px;
    color: #999;
  }
  .action-bar .btn:not(:first-child) {
    margin-left: 10px;
  }
  .btn:hover {
    color: #ccc;
    filter: drop-shadow(1px 1px 5px #000);
    cursor: pointer;
  }
  .action-bar .btn:active {
    filter: none !important;
  }
  .action-bar .btn.disabled {
    color: #666;
    pointer-events: none;
  }
  .action-bar .page-num {
    font-size: 22px;
    margin-left: 10px;
    color: $white-1;
  }
  .viewport {
    width: 90vw;
    height: calc(100vh - 150px);
    margin: auto;
  }
  .flipbook .bounding-box {
    box-shadow: 0 0 20px #000;
  }
}
@media (max-width: 600px) {
  .desc {
    font-size: 18px;
  }
  .flipbook {
    .viewport {
      height: calc(85vh - 150px);
      padding: 0;
    }
  }
}
</style>
