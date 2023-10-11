<template>
  <div class="contacts">
    <div class="contacts-title">DAVIDFISHER.RU</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "contactsView",
});
</script>

<style lang="scss" scoped>
@import "@/styles/variables.scss";
.contacts {
  height: 100vh;
  width: 90%;
  position: relative;
  display: flex;
  flex-direction: column;
  margin: auto;
  overflow-y: scroll;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  &-title {
    margin-top: 150px;
    font-size: 48px;
    font-weight: 700;
    // background-image: linear-gradient(180deg, #cccccc, #fc0000, #000000, #000);
    background-image: url("@/assets/fishka.png");
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
  }
  @media screen and (max-width: 600px) {
    &-title {
      font-size: 40px;
      margin-top: 30px;
    }
  }
  @media screen and (max-width: 380px) {
    &-title {
      font-size: 34px;
    }
  }
}
.contacts::-webkit-scrollbar {
  display: none;
}

@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }
  50% {
    transform: rotate(180deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
