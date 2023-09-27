<template>
  <div class="home">
    <div class="home-title">DAVIDFISHER.RU</div>
    <div class="router-list">
      <button>
        <router-link to="/about"
          ><span class="left-fishka"></span> Обо мне
          <span class="right-fishka"></span
        ></router-link>
      </button>
      <button>
        <router-link to="/book"
          ><span class="left-fishka"></span> Книга памяти
          <span class="right-fishka"></span
        ></router-link>
      </button>
      <button>
        <router-link to="/book"
          ><span class="left-fishka"></span> Игры
          <span class="right-fishka"></span
        ></router-link>
      </button>
      <button>
        <router-link to="/book"
          ><span class="left-fishka"></span> Реклама
          <span class="right-fishka"></span
        ></router-link>
      </button>
      <button>
        <router-link to="/book"
          ><span class="left-fishka"></span> Контакты
          <span class="right-fishka"></span
        ></router-link>
      </button>
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
@import "@/styles/variables.scss";
.home {
  height: 100vh;
  width: 90%;
  position: relative;
  display: flex;
  flex-direction: column;
  margin: auto;
  overflow-y: scroll;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  .router-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 30px;
    button {
      position: relative;
      display: flex;
      width: 280px;
      height: 40px;
      margin-top: 30px;
      border: 1px solid white;
      outline: none;
      transition: all 0.25s ease;
      border-radius: 20px;
      background: black;
      a {
        position: relative;
        margin: auto;
        width: 100%;
        text-decoration: none;
        font-weight: 500;
        font-size: 20px;
        color: white;
        span {
          position: absolute;
          opacity: 0;
          width: 25px;
          height: 25px;
          background-image: url("@/assets/fishka.png");
          background-repeat: no-repeat;
          background-size: contain;
          transition: all 0.25s ease;
          filter: brightness(125%);
          animation: rotate 3s linear infinite;
        }
        .left-fishka {
          left: 10%;
        }
        .right-fishka {
          right: 10%;
        }
      }
      &:hover {
        cursor: pointer;
        transform: scale(1.25);
        span {
          opacity: 1;
        }
      }
    }
  }
  &-title {
    margin-top: 150px;
    font-size: 48px;
    font-weight: 700;
    background-image: linear-gradient(180deg, #000000, #fc0000, #000000, #000);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
  }
}
.home::-webkit-scrollbar {
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
