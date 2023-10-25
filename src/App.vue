<template>
  <div id="app">
    <SearchRentalProperty />
  </div>
</template>

<script>
import SearchRentalProperty from './components/SearchRentalProperty.vue';

export default {
  name: 'App',
  components: {
    SearchRentalProperty
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
