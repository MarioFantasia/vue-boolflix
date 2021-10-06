<template>
  <div id="app">
    <Header @search="searchItem"></Header>
    <h2 style="color:red">FILMS</h2>
    <Films :propsFilm="takeFilm"></Films>
    <h2 style="color:red">SERIES</h2>
    <Series :propsSerie="takeSerie"></Series>
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
        takeFilm : "",
        takeSerie : ""
      }
    },

    methods : {
      searchItem(item) {
        this.takeFilm = item;
        this.takeSerie = item;
      }
    }
}
</script>

<style lang="scss">

</style>


