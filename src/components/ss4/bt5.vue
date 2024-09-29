<template>
  <div>
    <ul>
      <li>mèn mén loại 1 - số lượng: {{ menmen1 }}<button @click="increaseMenmen1">tăng</button></li>
      <li>mèn mén loại 2 - số lượng: {{ menmen2 }}<button @click="increaseMenmen2">tăng</button></li>
      <li>mèn mén loại 3 - số lượng: {{ menmen3 }}<button @click="increaseMenmen3">tăng</button></li>
    </ul>
    <h2>Tổng số mèn mén: {{ totalMenmen }}</h2>
  </div>
</template>

<script setup>
import { computed, ref } from "vue";

const menmen1 = ref(0);
const menmen2 = ref(0);
const menmen3 = ref(0);

const increaseMenmen1 = () => {
  menmen1.value++;
};

const increaseMenmen2 = () => {
  menmen2.value++;
};

const increaseMenmen3 = () => {
  menmen3.value++;
};

const totalMenmen = computed(
  () => menmen1.value + menmen2.value + menmen3.value
);
</script>

<style>

</style>