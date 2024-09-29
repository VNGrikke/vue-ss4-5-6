<template>
  <div>
    <input min="0" type="number" v-model.number="inputValue" />
    <button @click="calculate">caculate</button>
    <p>bình phương: {{ total }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";

const inputValue = ref(0);
const total = ref(0);

const calculate = () => {
  total.value = inputValue.value**2;
};

watch(inputValue, (newVal) => {
    console.log(newVal);
});
</script>

<style>

</style>