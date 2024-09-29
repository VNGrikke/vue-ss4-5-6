<template>
  <div>
    <button v-if="isShow" @click="handleClick">hiện</button>
    <button v-else @click="handleClick">ẩn</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isShow = ref(true);

const handleClick = () => {
  isShow.value = !isShow.value;
};
</script>

<style>
</style>