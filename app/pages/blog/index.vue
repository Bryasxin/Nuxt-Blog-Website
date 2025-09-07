<template>
  <div>
    <h1>博客归档</h1>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <NuxtLink :to="`/blog${post.path}`">{{ post.title }}</NuxtLink>
        <span> - {{ post.date }}</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
const { data: posts } = await useAsyncData("blog-archive", () =>
  queryCollection("content").all()
);

useHead({
  title: title("博客归档"),
});
</script>
