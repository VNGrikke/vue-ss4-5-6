<template>
  <div>
    <div>giới tính: {{ gender }}</div>
    <button @click="handleClick">random gender</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const gender = ref("nam");

const handleClick = () => {
  const genders = ["nam", "nữ"];
  gender.value = genders[Math.floor(Math.random() * genders.length)];
};
</script>

<style>
</style>