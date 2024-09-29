<template>
  <div>
    <button @click="handleClick">Show Notification</button>

    <div v-show="isShow" class="notification">
      <div>Mai nghỉ học</div>
      <div @click="handleClose" class="close-btn">x</div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isShow = ref(false);

let timeout = null;

const handleClick = () => {
  isShow.value = true;

  clearTimeout(timeout);

  timeout = setTimeout(() => {
    isShow.value = false;
  }, 5000);
};

const handleClose = () => {
  clearTimeout(timeout);
  isShow.value = false;
};
</script>

<style>
.notification {
  position: fixed;
  top: 10px;
  left: 10px;
  width: 300px;
  height: 50px;
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
  border-radius: 5px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  opacity: 1;
  transition: opacity 0.3s ease;
}

.close-btn {
  cursor: pointer;
}

[v-show="false"] {
  opacity: 0;
}
</style>
