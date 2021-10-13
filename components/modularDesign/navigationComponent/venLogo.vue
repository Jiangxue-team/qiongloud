<template>
  <div style="height: 100%;display: flex;">
    <img :src="this.img" class="vavigation-ul__logo"/>
  </div>
</template>

<script>
export default {
name: "venLogo",
  props: ['img']
}
</script>

<style scoped>
.vavigation-ul__logo {
  height: 100%;
  width: 165px;
}
</style>