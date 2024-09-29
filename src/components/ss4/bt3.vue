<template>
  <div>
    <div>dien tich: {{ calculate }}</div>
    <button @click="increaseWidth">click</button>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const width = ref(10);
const height = ref(20);

const calculate = computed(() => width.value * height.value);

const increaseWidth = () => {
  width.value += 10;
};
</script>

<style>
</style>
