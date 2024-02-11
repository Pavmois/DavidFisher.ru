<template>
  <div class="main-title">
    <router-link to="/">DAVIDFISHER.RU</router-link>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.main-title {
  position: relative;
  padding-top: 50px;
  a {
    font-size: 48px;
    font-weight: 700;
    // background-image: linear-gradient(180deg, #cccccc, #fc0000, #000000, #000);
    // background-image: url("@/assets/fishka.png");
    background-color: white;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
    @media screen and (max-width: 600px) {
      font-size: 40px;
      margin-top: 30px;
    }
  }
}
</style>
