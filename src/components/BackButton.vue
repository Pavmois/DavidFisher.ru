<template>
  <div class="back">
    <router-link to="/">На главную</router-link>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.back {
  position: fixed;
  bottom: 15px;
  left: 15px;
  background: black;
  border-radius: 20px;
  padding: 10px;
  font-size: 1rem;
  a {
    text-decoration: none;
    color: white;
  }
}
</style>
