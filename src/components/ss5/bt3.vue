<template>
  <div>
    <p>Quyền hạn của bạn là: {{ userRole }}</p>
    <button @click="handleClick">thay đổi</button>
  </div>
</template>

<script setup>

import { ref } from "vue";
const userRole = ref("guest");
const roles = ["admin", "user", "guest"];

const handleClick = () => {
  const randomIndex = Math.floor(Math.random() * roles.length);
  userRole.value = roles[randomIndex];
};
</script>

<style>
</style>