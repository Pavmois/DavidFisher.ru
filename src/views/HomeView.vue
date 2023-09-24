<template>
  <div class="home">
    <img alt="Vue logo" src="@/assets/logo.svg" />
    <div class="router-list">
      <button><router-link to="/about">Обо мне</router-link></button>
      <button><router-link to="/about">Книга памяти</router-link></button>
      <button><router-link to="/about">Обо мне</router-link></button>
      <button><router-link to="/about">Обо мне</router-link></button>
      <button><router-link to="/about">Контакты</router-link></button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",
});
</script>

<style lang="scss" scoped>
.home {
  margin: auto;
  width: 90%;
  height: 100vh;
  img {
    width: 300px;
  }
  .router-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    button {
      width: 280px;
      height: 40px;
      margin-top: 30px;
      border: 1px solid white;
      outline: none;
      transition: all 0.25s ease;
      border-radius: 20px;
      background: black;
      a {
        text-decoration: none;
        font-weight: bold;
        font-size: 22px;
        color: #2ceebd;
      }
      &:hover {
        cursor: pointer;
        &:nth-child(odd) {
          transform: scale(1.2) translateX(25%);
        }
        &:nth-child(even) {
          transform: scale(1.2) translateX(-25%);
        }
      }
    }
  }
}
</style>
