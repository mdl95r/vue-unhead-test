<template>
  <div>Это детальная страница события {{ route.params.eventCode }}</div>
</template>

<script setup>
import { useHead } from "@unhead/vue";
import { shallowRef, watch } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();

new Promise((resolve) => {
  setTimeout(() => {
    resolve(["ProbegSonkran", "ZabegKASKAD"]);
  }, 1500);
}).then((data) => {
  noIndexEventCodes.value = data;
});

const noIndexEventCodes = shallowRef(null);

const entry = useHead({
  title: `EventDetail - ${route.params.eventCode}`,
});

watch(
  () => window.YandexRotorSettings.IsLoaded,
  (bool) => {
    console.log("YandexRotorSettings.IsLoaded", bool);
  },
  { immediate: true }
);

watch(
  () => noIndexEventCodes.value,
  (codes) => {
    if (codes !== null && codes.includes(route.params.eventCode)) {
      entry.patch({ meta: [{ name: "robots", content: "noindex" }] });
    }

    window.YandexRotorSettings.IsLoaded = true;
    console.log(
      "YandexRotorSettings.IsLoaded",
      window.YandexRotorSettings.IsLoaded
    );
  },
  { immediate: true }
);
</script>

<style lang="scss" scoped></style>
