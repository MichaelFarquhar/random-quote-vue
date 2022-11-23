<script setup>
import axios from "axios";
import { onMounted, ref } from "vue";
import { themeChange } from "theme-change";

import TheGithubLink from "./components/TheGithubLink.vue";
import TheThemeSelect from "./components/TheThemeSelect.vue";
import TheQuoteDisplay from "./components/TheQuoteDisplay.vue";

let quote = ref({});
const isLoading = ref(true);

onMounted(() => {
  themeChange(false);

  // Get quote from API
  axios.get("https://api.quotable.io/random").then((resp) => {
    quote.value = resp.data;
    isLoading.value = false;
  });
});
</script>

<template>
  <main class="app bg-base-200">
    <TheThemeSelect />
    <div className="card bg-base-100 shadow-xl w-10/12 lg:w-6/12">
      <div className="card-body text-center">
        <TheQuoteDisplay
          :content="quote.content"
          :author="quote.author"
          :isLoading="isLoading"
        />
      </div>
    </div>
    <TheGithubLink />
  </main>
</template>
