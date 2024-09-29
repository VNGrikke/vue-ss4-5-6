<template>
  <button @click="handleClick">click {{count}} lần</button>
</template>

<script setup>
import {ref} from 'vue'
  const count = ref(0);
  const handleClick = () => {
    count.value++;
  }
</script>

<style>

</style>