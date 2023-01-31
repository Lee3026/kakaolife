<template>
  <div id="app">
    <appHeader />
    <router-view />
    <appFooter />
  </div>
</template>
<script>
import appHeader from './components/app-header';
import appFooter from './components/app-footer';

export default {
  name: 'App',
  components: {
    appHeader,
    appFooter
  }
}

</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
