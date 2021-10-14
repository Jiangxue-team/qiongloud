<template>
  <div class="navigation-word">
    <a @click="isNavigationLink" :id="title" style="width: auto;cursor: pointer">{{title}}<span style="padding-left: 4px">
      <svg width="16" height="11" viewBox="0 0 16 11" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M2 2L8.17143 8L14 2.33333" stroke="#E3E3E3" stroke-width="3"/>
        <path d="M8 8L14 2" stroke="#007FFF" stroke-width="3"/>
      </svg>
    </span></a>
    <div class="navigation-link" style="display: none;-webkit-transition-duration: 2s;" :id="this.son">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "vueSon",
  props: ['title','son'],
  methods: {
    isNavigationLink() {
        let venA= document.getElementById(this.title)
        let venBread = document.getElementById(this.son)
        venA.addEventListener('mousemove', function () {
          return venBread.style.display = 'inline-grid'
        })
        venBread.addEventListener('mouseleave', function () {
          return venBread.style.display = 'none'
        })
    }
  }
}
</script>

<style>
.navigation-word {
  display: inline-flex;
} @media screen and (max-width: 1025px) {
  .navigation-word {
    display: inline;
  }
}
.navigation-link {
  position: absolute;
  display: inline-grid;
  margin-top: 2em;
  text-align: left;
} @media screen and (max-width: 1024px) {
  .navigation-link {
    position: inherit;
    display: flow-root;
    margin-top: -77%;
    margin-bottom: 2%;
    padding-left: 4%;
  }
}
.navigation-link a {
  width: auto;
  margin-bottom: 1em;
} @media screen and (max-width: 1024px) {
  .navigation-link a {
    margin-bottom: -6%;
    padding-left: 1em;
  }
} @media screen and (max-width: 425px) {
  .navigation-link a {
    font-size: 16px;
  }
}
</style>