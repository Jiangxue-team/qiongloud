<template>
    <div class="overall" :style="{width: wide + '0%'}"><slot></slot></div>
</template>

<script>
export default {
  name: "venPer",
  props: {
    wide: String,
  }
}
</script>

<style scoped>
  .overall {
    line-height: 1.3em;
    white-space: inherit;
  }
</style>