<template>
  <div>
    <div> {{numbers}}  </div>
    <button @click="handleClick">tạo mảng ngẫu nhiên</button>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
const numbers = ref([]);
const handleClick = () => {
  const lengthArr = Math.floor(Math.random() * 11) + 10;
  const newNumbers = Array.from({ length: lengthArr }, () =>
    Math.floor(Math.random() * 100)
  );
  numbers.value = newNumbers;
};
</script>

<style>
</style>