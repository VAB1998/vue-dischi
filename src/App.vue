<template>
  <div id="app">
    <Header />
    <Albums />
  </div>
</template>

<script>
import Albums from './components/Albums.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
    Albums
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/variables.scss';

#app {
  
}
</style>