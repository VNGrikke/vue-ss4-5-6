<template>
  <div>
    <div>các số chẵn từ mảng</div>
    <div class="list">
      <span v-for="number in evenNumbers" :key="number">{{ number }} </span>
    </div>
    <button @click="handleClick">tạo mảng ngẫu nhiên</button>
  </div>
</template>

<script setup>
import { computed, ref } from "vue";

const numbers = ref([]);

const evenNumbers = computed(() => {
  return numbers.value.filter((number) => number % 2 === 0);
});

const handleClick = () => {
  const lengthArr = Math.floor(Math.random() * 11) + 10; 
  const newNumbers = Array.from({ length: lengthArr }, () => Math.floor(Math.random() * 100));
  numbers.value = newNumbers;
};
</script>

<style>
.list {
  display: flex;
  gap: 10px;
}
</style>
