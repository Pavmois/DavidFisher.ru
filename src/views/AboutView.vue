<template>
  <div class="about">
    <div class="about-list">
      <AccordeonList />
    </div>
  </div>
</template>

<script setup>
import AccordeonList from "@/components/AccordeonList.vue";
</script>

<style lang="scss" scoped>
.about {
  border: 1px solid red;
  height: 100vh;
  .about-list {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: space-around;
    margin-top: 150px;
  }
}
</style>
