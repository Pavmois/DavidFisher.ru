<template>
  <nav>
    <router-link to="/">Главная</router-link> |
    <router-link to="/about">Книга памяти</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>

<style lang="scss">
@import "@/styles/variables.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #7bff00;
}
html,
body {
  width: 100vw;
  overflow: hidden;
  margin: 0;
  padding: 0;
}
body {
  background: gray;
  // background: linear-gradient(-45deg, #ffffff44, #664656, #a13c3c, #000000);
  // background-size: 400% 400%;
  // animation: gradient 5s ease infinite;
}

nav {
  background: rgb(109, 158, 170);
  padding: 30px;

  a {
    font-weight: bold;
    color: #2ceebd;

    &.router-link-exact-active {
      color: #e00b0b;
    }
  }
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
</style>
