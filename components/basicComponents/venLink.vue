<template>
  <a :href="this.to" target="_blank" style="color: #0180FF" :style="{textDecoration: isBasicButton}" class="basic-style"><slot></slot>
    <img class="basic-style__img" :style="{display: isBasicIco}"
         src="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211019101641.png"></a>
</template>

<script>
export default {
name: "venLink",
  props: ["to","type"],
  data() {
    return {
      isBasicIco: this.basicStyle(),
      isBasicButton: this.basicButton()
    }
  },
  methods: {
    basicStyle() {
        if (this.type == 'ico') {
          return "inherit"
        }
        return "none"
      },
    basicButton() {
      if (this.type == 'nor') {
        return "none"
      }
      return "underline"
    }
  }
}
</script>

<style scoped>
.basic-style__img {
  cursor: pointer;
  width: 17px;
  vertical-align: middle;
  margin-left: 4px;
  color: #0180FF;
}
</style>