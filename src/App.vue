<template>
  <div id="app">
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Main from './components/macro/Main.vue';
import Footer from './components/macro/Footer.vue'
export default {
  name: 'App',
  components: {
    Main,
    Footer
  }
}
</script>

<style lang="scss">
</style>
