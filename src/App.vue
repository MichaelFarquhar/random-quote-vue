<script setup>
import { onMounted } from "vue";
import { themeChange } from "theme-change";

import TheGithubLink from "./components/TheGithubLink.vue";
import TheThemeSelect from "./components/TheThemeSelect.vue";

onMounted(() => {
  themeChange(false);
});
</script>

<template>
  <main>
    <TheThemeSelect />
    <h1>Test</h1>
    <TheGithubLink />
  </main>
</template>
