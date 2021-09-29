<template>
  <div id="app">
    <h1 class="text-success">Ciao</h1>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
#app {
  
}
</style>

// Create un nuovo progetto utilizzando Vue CLI
// Definite i componenti necessari per strutturare il layout come da screenshot allegato.
// Al caricamento della pagina, effettuate una chiama ajax all'API di boolean: https://flynn.boolean.careers/exercises/api/array/music
// E con i dati restituiti, stampate una card per ogni disco musicale.