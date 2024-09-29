<template>
  <div>
    <button @click="increase">tăng dần</button>
    <button @click="decrease">giảm dần</button>
    <div class="list">
      <span v-for="number in numbers" :key="number">{{ number }} </span>
    </div>
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

const increase = () => {
  numbers.value = numbers.value.sort((a, b) => a - b);
};

const decrease = () => {
  numbers.value = numbers.value.sort((a, b) => b - a);
};
</script>

<style>
</style>