<template>
  <div id="app">
    <header-header></header-header>
    <twetter-section></twetter-section>
  </div>
</template>

<script>
import TwetterSection from "./components/TwetterSection.vue";
import HeaderHeader from "./components/HeaderHeader.vue";

export default {
  name: 'App',
  components: {
    TwetterSection,
    HeaderHeader,
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  align-content: center;
  justify-content: center;
  /* still tried to fix to look nice, still failed */
}
</style>
