<template>
  <div>
    <h3>Danh sách bài viết</h3>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <div>id: {{ post.id }}</div>
        <div>title: {{ post.title }}</div>
        <div>content: {{ post.content }}</div>
        <div>author: {{ post.author }}</div>
        <div>_______________________________</div>
      </li>
    </ul>
  </div>
</template>

<script setup>
const posts = [
  {
    id: 1,
    title: "Post 1",
    content: "Nội dung bài viết 1",
    author: "Tác giả 1",
  },
  {
    id: 2,
    title: "Post 2",
    content: "Nội dung bài viết 2",
    author: "Tác giả 2",
  },
  {
    id: 3,
    title: "Post 3",
    content: "Nội dung bài viết 3",
    author: "Tác giả 3",
  },
];
</script>

<style>
ul {
  list-style-type: none;
  font-weight: 700;
}
</style>