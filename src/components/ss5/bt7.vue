<template>
  <div>
    <button :key="1" :class="{ active: activeIndex === 1 }" @click="handleClick(1)">Button 1</button>
    <button :key="2" :class="{ active: activeIndex === 2 }" @click="handleClick(2)">Button 2</button>
    <button :key="3" :class="{ active: activeIndex === 3 }" @click="handleClick(3)">Button 3</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const activeIndex = ref(1);

const handleClick = (index) => {
  activeIndex.value = index;
};
</script>

<style>
button {
  margin: 10px;
  padding: 8px 16px;
  font-size: 16px;
  cursor: pointer;
}

.active {
  background-color: red;
  color: #fff;
}
</style>
