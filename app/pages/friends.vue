<template>
  <div>
    <p>友链</p>
    <ul>
      <li v-for="link in links" :key="link.to">
        <NuxtLink :to="link.to">{{ link.content }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
const links = friendLinks();
</script>

<style></style>
