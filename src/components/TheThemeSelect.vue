<script setup>
import { themes } from "../themes.js";

const capitalize = (str) => {
  return str.charAt(0).toUpperCase() + str.slice(1);
};
</script>

<template>
  <div className="w-10/12 lg:w-6/12 mb-6">
    <div className="form-control max-w-xs">
      <label className="label">
        <span className="label-text">Change theme</span>
      </label>
      <select
        className="select select-bordered select-sm max-w-fit"
        data-choose-theme
      >
        <option v-for="theme in themes" :value="theme" :key="theme">
          {{ capitalize(theme) }}
        </option>
      </select>
    </div>
  </div>
</template>
