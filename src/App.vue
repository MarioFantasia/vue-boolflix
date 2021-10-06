<template>
  <div id="app">
    <Header @search="searchFilm"></Header>
    <h2>FILMS</h2>
    <Films :propsFilm="takeFilm"></Films>
    <h2>SERIES</h2>
    <Series></Series>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue'; 
import Series from './components/Series.vue'
export default {
    components : {
      Header,
      Films,
      Series
    },

    data() {
      return {
        takeFilm : ""
      }
    },

    methods : {
      searchFilm(film) {
        this.takeFilm = film;
      }
    }
}
</script>

<style lang="scss">

</style>


