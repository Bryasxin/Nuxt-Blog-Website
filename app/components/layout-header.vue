<script lang="ts" setup>
const links = headerLinks();
</script>

<template>
  <div class="root">
    <div class="icon">HalFLinE's Website</div>
    <div class="links">
      <NuxtLink v-for="link in links" :key="link.to" :to="link.to" class="link">
        {{ link.content }}
      </NuxtLink>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.root {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 0.5rem;
  border-bottom: 1px solid gray;
  display: flex;
  align-items: center;
}

.icon {
  font-weight: bold;
  font-size: 1.5rem;
  margin: 0.25rem 0;
}

.links {
  margin-left: auto;
  display: flex;

  .link {
    margin: 0 0.5rem;
    text-decoration: none;
    position: relative;
    color: black;

    &:hover {
      text-decoration: underline;
    }
  }
}
</style>
