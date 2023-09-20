<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
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
body {
  background: darkgray;
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
</style>
