<template>
  <div>
    <ul :class="[isVavigationLinkSpan ? vavigationLiSpan : '', vavigationShowLoaf]"  @click="isVavigationUlMod">
      <li class="vavigation-li__med">
        <span style="background: #007FFF" class="vavigation-li__span1" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
        <span style="background: #E3E3E3" class="vavigation-li__span2" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
        <span style="background: #E3E3E3" class="vavigation-li__span3" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
      </li>
    </ul>
    <ul class="vavigation-ul__med" id="ven-bread" @click="isVavigationLinkClickHide" style="cursor: pointer">
      <li class="vavigation-li__a a"><slot></slot></li>
    </ul>
  </div>
  <div>
  </div>
</template>

<script>
export default {
name: "vBread",
  props: {
    loaf: Boolean,
    img: String
  },
  data() {
    return {
      isVavigationLinkSpan: this.loaf,
      vavigationLiSpan: 'vavigationLi__span',
      vavigationShowLoaf: 'vavigationShow__loaf',
    }
  },
  methods: {
    isVavigationUlMod() {
      let venBread = document.getElementById('ven-bread')
      return venBread.style.left = '0%'
    },
    isVavigationLinkClickHide() {
      let venBread = document.getElementById('ven-bread')
      return venBread.style.left = '-100%'
    }
  }
}
</script>

<style>
.vavigation-li__a a {
  padding: 0 12px;
} @media screen and (max-width: 1024px) {
  .vavigation-li__a a {
    margin: 2em;
    display: table;
  }
} @media screen and(max-width: 452px) {
  .vavigation-li__a a {
    font-size: 17px;
  }
}
.vavigation-li__a a:hover {
  color: #007FFF;
  border-bottom: 5px solid #007FFF;
  -webkit-transition-duration: 0.3s;
}
</style>

<style scoped>
li {
  list-style: none;
}
@media screen and (max-width: 1024px) {
  .vavigation-li__med {
    display: inline-grid;
    cursor: pointer;
  }
}
@media screen and (max-width: 1024px) {
  .vavigation-ul__med {
    text-align: -webkit-left;
    left: 0;
    background: #fafafa;
    width: 50%;
    height: 100%;
    position: absolute;
    top: 0%;
    margin: 0;
    left: -100%;
    -webkit-transition-duration: 0.7s;
  }
}
.vavigation-li__span {
  width: 44px;
  height: 4px;
  border: white 3px solid;
  display: none;
} @media screen and (max-width: 1024px) {
  .vavigation-li__span {
    display: table;
    cursor: pointer;
  }
}
.vavigation-show__loaf {
  display: none;
}
li span:hover {
  width: 10px;
  -webkit-transition-duration: 2s;
}
.vavigation-link {
  padding: 0 12px;
}
.vavigation-link:hover {
  color: #007FFF;
}@media screen and (max-width: 1024px) {
  .vavigation-link {
    display: none;
  }
}
</style>