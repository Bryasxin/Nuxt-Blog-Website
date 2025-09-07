<template>
  <div class="root">
    <LayoutHeader />
    <slot />
  </div>
</template>

<style lang="scss" scoped>
.root {
  max-width: 1200px;
  margin: 0 auto;
}
</style>