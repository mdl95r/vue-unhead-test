<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script setup>
import { useHead } from "@unhead/vue";
import HelloWorld from "@/components/HelloWorld.vue";

useHead({
  title: "Home",
});
</script>
