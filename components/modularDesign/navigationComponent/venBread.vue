<template>
  <div>
    <ul :class="[isVavigationLinkSpan ? vavigationLiSpan : '', vavigationShowLoaf]"  @click="isVavigationUlMod">
      <li class="vavigation-li__med">
        <span style="background: #007FFF" class="vavigation-li__span1" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
        <span style="background: #E3E3E3;margin-top: 7px;margin-bottom: 7px;" class="vavigation-li__span2" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
        <span style="background: #E3E3E3" class="vavigation-li__span3" :class="{'vavigation-li__span':isVavigationLinkSpan}"></span>
      </li>
    </ul>
    <ul class="vavigation-ul__med" id="ven-bread">
      <div id="ven-close" @click="isVavigationLinkClickHide" class="vavigation-ui__close" style="cursor: pointer">
        <svg width="39" height="23" viewBox="0 0 39 23" fill="none" xmlns="http://www.w3.org/2000/svg" >
          <path fill-rule="evenodd" clip-rule="evenodd" d="M38.9993 14H3.99927V9.99997H38.9993V14Z" fill="#007FFF"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M0.162757 12.3975L11.4056 0.828864L14.1987 3.5474L2.95584 15.116L0.162757 12.3975Z" fill="#E3E3E3"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M13.6794 20.2289L4.70493 11.2545L2.04321 13.9162L11.0176 22.8906L13.6794 20.2289Z" fill="#E3E3E3"/>
        </svg>
      </div>
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
       return venBread.style.left = '-490%'
    }
  }
}
</script>

<style>
.vavigation-ui__close {
  display: none;
} @media screen and (max-width: 1024px) {
  .vavigation-ui__close {
    margin-top: 9%;
    display: inline-table;
  }
}
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
  -webkit-transition-duration: 0.6s;
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
.vavigation-ul__med {
  line-height: 1.3;
}
@media screen and (max-width: 1024px) {
  .vavigation-ul__med {
    text-align: -webkit-left;
    left: 0;
    background: #fafafa;
    width: auto;
    height: 100%;
    overflow: auto;
    position: absolute;
    top: 0%;
    margin: 0;
    left: -420%;
    -webkit-transition-duration: 0.7s;
  }
}
.vavigation-li__span {
  width: 44px;
  height: 4px;
  display: none;
} @media screen and (max-width: 1024px) {
  .vavigation-li__span {
    display: table;
    cursor: pointer;
  }
  @media screen and(max-width: 425px) {
    .vavigation-li__span {
      width: 36px;
      height: 3px;
    }
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