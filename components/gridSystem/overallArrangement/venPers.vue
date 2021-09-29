<template>
  <div class="overall" :style="{width: wide + '%'}"><slot></slot></div>
</template>

<script>
export default {
  name: "venPers",
  props: {
    wide: String
  }
}
</script>

<style scoped>
.overall {
  line-height: 1.3em;
  white-space: inherit;
  max-width: 100%;
}
</style>