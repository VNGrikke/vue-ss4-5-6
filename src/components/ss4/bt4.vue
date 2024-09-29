<template>
  <div>
    <input type="text" v-model="inputValue" />
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const inputValue = ref("");

watch(inputValue, (newValue) => {
  console.log("Giá trị đã thay đổi:", newValue);
});
</script>

<style>
</style>