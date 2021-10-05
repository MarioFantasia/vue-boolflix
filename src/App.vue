<template>
  <div id="app">
    <Header @search="searchFilm"></Header>
    <Films :infoProps="takeFilm"></Films>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue'; 
export default {
    components : {
      Header,
      Films
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


