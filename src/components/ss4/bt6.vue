<template>
  <div>
    <input min="0" type="number" v-model.number="inputValue" />
    <button @click="addToCart">Add to cart</button>
    <p>Tổng tiền: {{ total }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const inputValue = ref(0);
const total = ref(0);

const addToCart = () => {
  total.value += inputValue.value;
};
</script>

<style>
</style>