<template>
  <div>
    <h1>友链</h1>
    <ul>
      <li v-for="link in links" :key="link.to">
        <NuxtLink :to="link.to">{{ link.content }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
useSeoMeta({
  title: title("友链"),
});

const links = friendLinks();
</script>
