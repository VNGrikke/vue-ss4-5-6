<template>
  <div>
    <button @click="handleClick1">hiển thị</button>
    <button @click="handleClick2">ẩn</button>
    <div v-if="isShow">
      <b>welcome to rekkei education</b>
    </div>
  </div>
</template>

<script setup>
  import { ref } from 'vue';
  const isShow = ref(false);
  const handleClick1 = () => {
    isShow.value = true;
  };
  const handleClick2 = () => {
    isShow.value = false;
  };
</script>

<style>

</style>