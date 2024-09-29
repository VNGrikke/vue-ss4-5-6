<template>
  <div>
    <div>
      <input type="text" v-model="productName" placeholder="Tên sản phẩm" />
      <input type="number" v-model.number="productQuantity" min="0" placeholder="Số lượng" />
      <button @click="addProduct">Thêm vào giỏ</button>
    </div>
    <ul>
      <li v-for="product in products" :key="product.name">
        {{ product.name }} - Số lượng: {{ product.quantity }}
      </li>
    </ul>
    <p>Tổng số lượng sản phẩm: {{ totalQuantity }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const productName = ref('');
const productQuantity = ref(0);
const products = ref([]);

const addProduct = () => {
  products.value.push({
    name: productName.value,
    quantity: productQuantity.value,
  });
  productName.value = '';
  productQuantity.value = 0;
};

const totalQuantity = computed(() => {
  return products.value.reduce((total, product) => total + product.quantity, 0);
});
</script>

<style>

</style>