<template>
  <div>
    <button @click="handleClick1">hiển thị</button>
    <button @click="handleClick2">ẩn</button>
    <div v-if="show">
      <p>Nội dung hiển thị</p>
    </div>
    <div v-else>
      <p>Nội dung ẩn</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const show = ref(false);
const handleClick1 = () => {
  show.value = true;
};
const handleClick2 = () => {
  show.value = false;
};
</script>

<style>
</style>