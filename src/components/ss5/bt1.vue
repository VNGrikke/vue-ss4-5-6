<template>
  <div>
    <button @click="handleChange">hiện</button>
    <div v-if="show">Hello Rikkei</div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const show = ref(false);
const handleChange = () => {
  show.value = true;
};
</script>

<style>
</style>