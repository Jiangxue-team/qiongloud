<template>
  <div :style="{gridTemplate: isRepeat}" id="v-con" style="display: grid;"><slot></slot></div>
</template>

<script>
export default {
  name: "venHeader",
  data() {
    return {
      isRepeat: 'repeat(1,auto)/repeat(' + this.gapsSpan() + ',minmax(auto, 100%))'
    }
  },
  props: ['gap'],
  methods: {
    gapsSpan() {
        let p768 = window.matchMedia('(max-width: 768px)')
        let p1024 = window.matchMedia('(max-width: 1024px)')
        let p425 = window.matchMedia('(max-width: 425px)')
        let p320 = window.matchMedia('(max-width: 320px)')
        if(this.gap <=2) {
          this.$nextTick(() => {
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 2
        }
        if(this.gap <= 3) {
          this.$nextTick(() => {
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 3
        }
        if(this.gap <= 4) {
          this.$nextTick(() => {
              if (p320.matches) {
                this.gapsSpan320__10
              }
          })
          return 4
        }
        if(this.gap <= 5) {
          this.$nextTick(() => {
            if (p425.matches) {
              this.gapsSpan768__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 5
        }
        if(this.gap <= 6) {
          this.$nextTick(() => {
            if (p768.matches) {
              this.gapsSpan768__10
            }
            if (p425.matches) {
              this.gapsSpan425__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 6
        }
        if(this.gap <= 7) {
          this.$nextTick(() => {
            if (p768.matches) {
              this.gapsSpan768__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 7
        }
        if(this.gap <= 8) {
          this.$nextTick(() => {
            if (p768.matches) {
              this.gapsSpan768__10
            }
            if (p1024.matches) {
              this.gapsSpan1024__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 8
        }
        if(this.gap <= 9) {
          this.$nextTick(() => {
            if (p1024.matches) {
              this.gapsSpan768__10
            }
            if (p425.matches) {
              this.gapsSpan425__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 9
        }
        if(this.gap >=10) {
          this.$nextTick(() => {
            if (p1024.matches) {
              this.gapsSpan1024__10
            }
            if (p768.matches) {
              this.gapsSpan768__10
            }
            if (p425.matches) {
              this.gapsSpan425__10
            }
            if (p320.matches) {
              this.gapsSpan320__10
            }
          })
          return 10
        }
    }
  },
  computed: {
    gapsSpan1024__10() {
      return document.getElementById('v-con').style.gridTemplate = 'repeat(1,auto)/repeat(4,minmax(auto, 100%))'
    },
    gapsSpan768__10() {
      return document.getElementById('v-con').style.gridTemplate = 'repeat(1,auto)/repeat(3,minmax(auto, 100%))'
    },
    gapsSpan425__10() {
      return document.getElementById('v-con').style.gridTemplate = 'repeat(1,auto)/repeat(2,minmax(auto, 100%))'
    },
    gapsSpan320__10() {
      return document.getElementById('v-con').style.gridTemplate = 'repeat(1,auto)/repeat(2,minmax(auto, 100%))'
    }
  }
}
</script>

<style scoped>
  .overall-con {

  }
</style>