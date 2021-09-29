<template>
  <div id="app">
    <Albums />
  </div>
</template>

<script>
import Albums from './components/Albums.vue'

export default {
  name: 'App',
  components: {
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

// Create un nuovo progetto utilizzando Vue CLI
// Definite i componenti necessari per strutturare il layout come da screenshot allegato.
// Al caricamento della pagina, effettuate una chiama ajax all'API di boolean: https://flynn.boolean.careers/exercises/api/array/music
// E con i dati restituiti, stampate una card per ogni disco musicale.