<template>
  <div :style="{textAlign: site}" class="overall-main"><slot></slot></div>
</template>

<script>
export default {
  name: "venMain",
  props: ['site']
}
</script>

<style scoped>
.overall-main {
  word-wrap: break-word;
}
</style>