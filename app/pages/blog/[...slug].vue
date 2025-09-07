<template>
  <div v-if="data" class="blog-post">
    <h1>{{ data.title }}</h1>
    <p>发布日期: {{ data.date }}</p>

    <!-- eslint-disable-next-line vue/no-v-html -->
    <ContentRenderer :value="data" />
  </div>
  <div v-else>
    <p>文章未找到</p>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute();
const slugPath = Array.isArray(route.params.slug)
  ? route.params.slug.join("/")
  : (route.params.slug ?? "");

const { data } = await useAsyncData(`blog-${slugPath}`, () =>
  queryCollection("content").path(`/${slugPath}`).first()
);

if (data.value) {
  useHead({
    title: data.value.title,
  });
}

if (!data.value && import.meta.server) {
  throw createError({
    statusCode: 404,
    statusMessage: "页面不存在",
  });
}
</script>
