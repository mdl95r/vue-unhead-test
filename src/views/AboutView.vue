<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<script setup>
import { useHead } from "@unhead/vue";

useHead({
  title: "About",
  meta: [{ name: "robots", content: "noindex" }],
});
</script>
