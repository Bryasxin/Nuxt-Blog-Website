<script setup lang="ts">
const { data } = await useAsyncData(() => queryCollection('content').path('/').first())

useSeoMeta({
  title: data.value?.title,
  description: data.value?.description
})
</script>

<template>
  <ContentRenderer v-if="data" :value="data" />
  <div v-else>Home not found</div>
</template>
