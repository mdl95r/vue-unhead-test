<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/eventDetail/ProbegSonkran">ProbegSonkran</router-link> |
    <router-link to="/eventDetail/ZabegKASKAD">ZabegKASKAD</router-link> |
    <router-link to="/eventDetail/Vesenniyprobeg">Vesenniyprobeg</router-link>
  </nav>
  <router-view />
</template>

<script setup>
import { createHead } from "@unhead/vue";

createHead();
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
