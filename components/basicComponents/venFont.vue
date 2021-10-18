<template>
<p :style="{fontSize: isFontSize + 'px',lineHeight: isLineHeight}"><slot></slot></p>
</template>

<script>
export default {
name: "ven-font",
  props: ["size","row"],
  data() {
    return {
      isFontSize: this.fontSize(),
      isLineHeight: this.lineHeight()
    }
  },
  methods: {
    fontSize() {
      if (this.size == 'h1') {
        return '24'
      }
      if (this.size == 'h2') {
        return '22'
      }
      if (this.size == 'h3') {
        return '20'
      }
      if (this.size == 'h4') {
        return '18'
      }
      if (this.size == 'h5') {
        return '16'
      }
    },
    lineHeight() {
      if (this.row == '1') {
        return '1'
      }
      if (this.row == '0.5') {
        return '0.5'
      }
      if (this.row == '0.1') {
        return '0.1'
      }
    }
  }
}
</script>

<style scoped>

</style>