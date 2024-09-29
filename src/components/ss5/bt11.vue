<template>
  <div>
    <input type="text" v-model="inputValue" placeholder="tìm kiếm tên user" />
    <button @click="findUser">Tìm kiếm</button>
    <ul>
      <li v-for="user in filteredUsers" :key="user.id">
        {{ user.name }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const users = [
  { id: 1, name: "John Doe" },
  { id: 2, name: "Jane Doe" },
  { id: 3, name: "Alice Doe" },
  { id: 4, name: "Bob Smith" },
  { id: 5, name: "Charlie Johnson" },
  { id: 6, name: "Emily Davis" },
  { id: 7, name: "Franklin Miller" },
  { id: 8, name: "Grace Lee" },
  { id: 9, name: "Henry Clark" },
  { id: 10, name: "Isabella Taylor" },
];

const inputValue = ref("");

const filteredUsers = ref([...users]);

const findUser = () => {
  if (!inputValue.value) {
    filteredUsers.value = [...users];
  } else {
    filteredUsers.value = users.filter((user) =>
      user.name.toLowerCase().includes(inputValue.value.toLowerCase())
    );
  }
};
</script>

<style>
</style>
