<template>
  <div class="about">
    <div class="about-list">
      <AccordeonList />
    </div>
    <Back />
  </div>
</template>

<script setup>
import AccordeonList from "@/components/AccordeonList.vue";
import Back from "@/components/BackButton.vue";
</script>

<style lang="scss" scoped>
.about {
  margin: auto;
  width: 40%;
  height: 90vh;
  .about-list {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: space-around;
    margin-top: 150px;
  }
  @media screen and (max-width: 1024px) {
    width: 70%;
  }
  @media screen and (max-width: 550px) {
    width: 90%;
  }
}
</style>
