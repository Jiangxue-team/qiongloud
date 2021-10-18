<template>
  <color :style="{color: isColor,background: isBackColor}"><slot></slot></color>
</template>

<script>
export default {
name: "venColor",
  props: ['col','spa','back'],
  data() {
    return {
      isColor: this.colorOpt(),
      isBackColor: this.back || this.colorOpt()
    }
  },
  methods: {
    colorOpt() {
      // blue
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
      // green
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
      // white
      if (this.col == 'white' && this.spa == 1) {
        return '#fbfbfb'
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
      // black
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
      // yellow
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
      // red
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
      // green
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

<style scoped>

</style>