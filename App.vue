<template>
</template>

<script>
import VenPer from "./components/gridSystem/overallArrangement/venPer";
import VenPers from "./components/gridSystem/overallArrangement/venPers";

export default {
  name: 'App',
  components: {
    VenPers,
    VenPer,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #343434;
  margin-top: 60px;
}
body {
  width: 100%;
  margin: 0 auto;
}
</style>
