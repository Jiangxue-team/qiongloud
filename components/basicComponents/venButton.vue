<template>
  <button :style="{background: isBackColor,color: isColor,border: isBorder}" class="basic-button">
    <img :src="this.ico" class="basic-button__ico" :style="{display: isMarginRight}"/><slot></slot></button>
</template>
<style scoped>
.basic-button__ico {
  vertical-align: middle;
  margin-right: 10px;
}
.basic-button {
  padding: 9px 2.2em;
  width: auto;
  height: auto;
  border: none;
  border-radius: 1px;
  font-size: 16.5px;
  cursor: pointer;
  outline: none;
  background: rgb(251 251 251 / 0%);
}
.basic-button:hover {
  filter: brightness(105%);
  -webkit-transition-duration: 0.7s;
}
.basic-button:active {
  outline: none;
  -webkit-transition-duration: 0.3s;
}
</style>
<script>
export default {
name: "venButton",
  props: ['col','spa','back','font','ico'],
  data() {
    return {
      isColor:  this.colorFont(),
      isBackColor: this.back || this.colorOpt(),
      isBorder: `3px solid ` + this.colorFont(),
      isMarginRight: this.icoNull()
    }
  },
  methods: {
    icoNull() {
      if (this.ico == null) {
        return "none"
      }
      if (this.ico !== "") {
        return "unset"
      }
    },
    colorFont() {
// blue back
      if (this.font == 'blue' && this.spa == 1) {
        return '#007fff'
      }
      if (this.font == 'blue' && this.spa == 2) {
        return '#369aff'
      }
      if (this.font == 'blue' && this.spa == 3) {
        return '#66b2ff'
      }
      if (this.font == 'blue' && this.spa == 4) {
        return '#87c3ff'
      }
      if (this.font == 'blue' && this.spa == 5) {
        return '#99ccff'
      }
      if (this.font == 'blue' && this.spa == 6) {
        return '#b0d7ff'
      }
      if (this.font == 'blue' && this.spa == 7) {
        return 'rgb(194 224 255)'
      }
      if (this.font == 'blue' && this.spa == 8) {
        return 'rgb(212 234 255)'
      }
      if (this.font == 'blue' && this.spa == 9) {
        return 'rgb(232 243 255)'
      }
// green back
      if (this.font == 'blue-green' && this.spa == 1) {
        return '#00ffff'
      }
      if (this.font == 'blue-green' && this.spa == 2) {
        return '#36ffff'
      }
      if (this.font == 'blue-green' && this.spa == 3) {
        return '#66ffff'
      }
      if (this.font == 'blue-green' && this.spa == 4) {
        return '#87ffff'
      }
      if (this.font == 'blue-green' && this.spa == 5) {
        return '#99ffff'
      }
      if (this.font == 'blue-green' && this.spa == 6) {
        return '#b0ffff'
      }
      if (this.font == 'blue-green' && this.spa == 7) {
        return '#b0ffff'
      }
      if (this.font == 'blue-green' && this.spa == 8) {
        return '#d4ffff'
      }
      if (this.font == 'blue-green' && this.spa == 9) {
        return '#e8ffff'
      }
// white back
      if (this.font == 'white' && this.spa == 1) {
        return '#fbfbfb'
      }
      if (this.font == 'white' && this.spa == 2) {
        return '#e9e9e9'
      }
      if (this.font == 'white' && this.spa == 3) {
        return '#eeeeee'
      }
      if (this.font == 'white' && this.spa == 4) {
        return '#f2f2f2'
      }
      if (this.font == 'white' && this.spa == 5) {
        return '#f4f4f4'
      }
      if (this.font == 'white' && this.spa == 6) {
        return '#f6f6f6'
      }
      if (this.font == 'white' && this.spa == 7) {
        return '#f8f8f8'
      }
      if (this.font == 'white' && this.spa == 8) {
        return '#fbfbfb'
      }
      if (this.font == 'white' && this.spa == 9) {
        return 'rgb(251 251 251 / 0%)'
      }
// black back
      if (this.font == 'black' && this.spa == 1) {
        return '#000000'
      }
      if (this.font == 'black' && this.spa == 2) {
        return '#363636'
      }
      if (this.font == 'black' && this.spa == 3) {
        return '#666666'
      }
      if (this.font == 'black' && this.spa == 4) {
        return '#878787'
      }
      if (this.font == 'black' && this.spa == 5) {
        return '#999999'
      }
      if (this.font == 'black' && this.spa == 6) {
        return '#b0b0b0'
      }
      if (this.font == 'black' && this.spa == 7) {
        return '#c2c2c2'
      }
      if (this.font == 'black' && this.spa == 8) {
        return '#d4d4d4'
      }
      if (this.font == 'black' && this.spa == 9) {
        return '#e8e8e8'
      }
// yellow back
      if (this.font == 'yellow' && this.spa == 1) {
        return '#ffd600'
      }
      if (this.font == 'yellow' && this.spa == 2) {
        return '#ffdf36'
      }
      if (this.font == 'yellow' && this.spa == 3) {
        return '#ffe666'
      }
      if (this.font == 'yellow' && this.spa == 4) {
        return '#ffec87'
      }
      if (this.font == 'yellow' && this.spa == 5) {
        return '#ffef99'
      }
      if (this.font == 'yellow' && this.spa == 6) {
        return '#fff2b0'
      }
      if (this.font == 'yellow' && this.spa == 7) {
        return '#fff5c2'
      }
      if (this.font == 'yellow' && this.spa == 8) {
        return '#fff8d4'
      }
      if (this.font == 'yellow' && this.spa == 9) {
        return '#fffbe8'
      }
// red back
      if (this.font == 'red' && this.spa == 1) {
        return '#ff2e2e'
      }
      if (this.font == 'red' && this.spa == 2) {
        return '#ff3636'
      }
      if (this.font == 'red' && this.spa == 3) {
        return '#ff6666'
      }
      if (this.font == 'red' && this.spa == 4) {
        return '#ff8787'
      }
      if (this.font == 'red' && this.spa == 5) {
        return '#ff9999'
      }
      if (this.font == 'red' && this.spa == 6) {
        return '#ffb0b0'
      }
      if (this.font == 'red' && this.spa == 7) {
        return '#ffc2c2'
      }
      if (this.font == 'red' && this.spa == 8) {
        return '#ffd4d4'
      }
      if (this.font == 'red' && this.spa == 9) {
        return '#ffe8e8'
      }
// green back
      if (this.font == 'green' && this.spa == 1) {
        return '#00ff75'
      }
      if (this.font == 'green' && this.spa == 2) {
        return '#36ff92'
      }
      if (this.font == 'green' && this.spa == 3) {
        return '#66ffac'
      }
      if (this.font == 'green' && this.spa == 4) {
        return '#87ffbe'
      }
      if (this.font == 'green' && this.spa == 5) {
        return '#99ffc8'
      }
      if (this.font == 'green' && this.spa == 6) {
        return '#b0ffd4'
      }
      if (this.font == 'green' && this.spa == 7) {
        return '#c2ffde'
      }
      if (this.font == 'green' && this.spa == 8) {
        return '#d4ffe8'
      }
      if (this.font == 'green' && this.spa == 9) {
        return '#e8fff3'
      }
    },
    colorOpt() {
      // blue back
      if (this.col == 'blue' && this.spa == 1) {
        return '#007fff'
      }
      if (this.col == 'blue' && this.spa == 2) {
        return '#369aff'
      }
      if (this.col == 'blue' && this.spa == 3) {
        return '#66b2ff'
      }
      if (this.col == 'blue' && this.spa == 4) {
        return '#87c3ff'
      }
      if (this.col == 'blue' && this.spa == 5) {
        return '#99ccff'
      }
      if (this.col == 'blue' && this.spa == 6) {
        return '#b0d7ff'
      }
      if (this.col == 'blue' && this.spa == 7) {
        return 'rgb(194 224 255)'
      }
      if (this.col == 'blue' && this.spa == 8) {
        return 'rgb(212 234 255)'
      }
      if (this.col == 'blue' && this.spa == 9) {
        return 'rgb(232 243 255)'
      }
      // green back
      if (this.col == 'blue-green' && this.spa == 1) {
        return '#00ffff'
      }
      if (this.col == 'blue-green' && this.spa == 2) {
        return '#36ffff'
      }
      if (this.col == 'blue-green' && this.spa == 3) {
        return '#66ffff'
      }
      if (this.col == 'blue-green' && this.spa == 4) {
        return '#87ffff'
      }
      if (this.col == 'blue-green' && this.spa == 5) {
        return '#99ffff'
      }
      if (this.col == 'blue-green' && this.spa == 6) {
        return '#b0ffff'
      }
      if (this.col == 'blue-green' && this.spa == 7) {
        return '#b0ffff'
      }
      if (this.col == 'blue-green' && this.spa == 8) {
        return '#d4ffff'
      }
      if (this.col == 'blue-green' && this.spa == 9) {
        return '#e8ffff'
      }
      // white back
      if (this.col == 'white' && this.spa == 1) {
        return 'rgb(251 251 251 / 0%)'
      }
      if (this.col == 'white' && this.spa == 2) {
        return '#e9e9e9'
      }
      if (this.col == 'white' && this.spa == 3) {
        return '#eeeeee'
      }
      if (this.col == 'white' && this.spa == 4) {
        return '#f2f2f2'
      }
      if (this.col == 'white' && this.spa == 5) {
        return '#f4f4f4'
      }
      if (this.col == 'white' && this.spa == 6) {
        return '#f6f6f6'
      }
      if (this.col == 'white' && this.spa == 7) {
        return '#f8f8f8'
      }
      if (this.col == 'white' && this.spa == 8) {
        return '#fbfbfb'
      }
      if (this.col == 'white' && this.spa == 9) {
        return '#fcfcfc'
      }
      // black back
      if (this.col == 'black' && this.spa == 1) {
        return '#000000'
      }
      if (this.col == 'black' && this.spa == 2) {
        return '#363636'
      }
      if (this.col == 'black' && this.spa == 3) {
        return '#666666'
      }
      if (this.col == 'black' && this.spa == 4) {
        return '#878787'
      }
      if (this.col == 'black' && this.spa == 5) {
        return '#999999'
      }
      if (this.col == 'black' && this.spa == 6) {
        return '#b0b0b0'
      }
      if (this.col == 'black' && this.spa == 7) {
        return '#c2c2c2'
      }
      if (this.col == 'black' && this.spa == 8) {
        return '#d4d4d4'
      }
      if (this.col == 'black' && this.spa == 9) {
        return '#e8e8e8'
      }
      // yellow back
      if (this.col == 'yellow' && this.spa == 1) {
        return '#ffd600'
      }
      if (this.col == 'yellow' && this.spa == 2) {
        return '#ffdf36'
      }
      if (this.col == 'yellow' && this.spa == 3) {
        return '#ffe666'
      }
      if (this.col == 'yellow' && this.spa == 4) {
        return '#ffec87'
      }
      if (this.col == 'yellow' && this.spa == 5) {
        return '#ffef99'
      }
      if (this.col == 'yellow' && this.spa == 6) {
        return '#fff2b0'
      }
      if (this.col == 'yellow' && this.spa == 7) {
        return '#fff5c2'
      }
      if (this.col == 'yellow' && this.spa == 8) {
        return '#fff8d4'
      }
      if (this.col == 'yellow' && this.spa == 9) {
        return '#fffbe8'
      }
      // red back
      if (this.col == 'red' && this.spa == 1) {
        return '#ff2e2e'
      }
      if (this.col == 'red' && this.spa == 2) {
        return '#ff3636'
      }
      if (this.col == 'red' && this.spa == 3) {
        return '#ff6666'
      }
      if (this.col == 'red' && this.spa == 4) {
        return '#ff8787'
      }
      if (this.col == 'red' && this.spa == 5) {
        return '#ff9999'
      }
      if (this.col == 'red' && this.spa == 6) {
        return '#ffb0b0'
      }
      if (this.col == 'red' && this.spa == 7) {
        return '#ffc2c2'
      }
      if (this.col == 'red' && this.spa == 8) {
        return '#ffd4d4'
      }
      if (this.col == 'red' && this.spa == 9) {
        return '#ffe8e8'
      }
      // green back
      if (this.col == 'green' && this.spa == 1) {
        return '#00ff75'
      }
      if (this.col == 'green' && this.spa == 2) {
        return '#36ff92'
      }
      if (this.col == 'green' && this.spa == 3) {
        return '#66ffac'
      }
      if (this.col == 'green' && this.spa == 4) {
        return '#87ffbe'
      }
      if (this.col == 'green' && this.spa == 5) {
        return '#99ffc8'
      }
      if (this.col == 'green' && this.spa == 6) {
        return '#b0ffd4'
      }
      if (this.col == 'green' && this.spa == 7) {
        return '#c2ffde'
      }
      if (this.col == 'green' && this.spa == 8) {
        return '#d4ffe8'
      }
      if (this.col == 'green' && this.spa == 9) {
        return '#e8fff3'
      }
    }
  }
}
</script>

