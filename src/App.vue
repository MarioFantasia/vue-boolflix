<template>
  <div id="app">
    <Header @search="searchItem"></Header>
    <section class="main_section fel">
      <h2 v-if="this.takeFilm != ''" style="color:red">FILMS</h2>
      <Films :propsFilm="takeFilm"></Films>
      <h2 v-if="this.takeFilm != ''" style="color:red">SERIES</h2>
      <Series :propsSerie="takeSerie"></Series>
    </section>
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
  /* importo fontawesome */
  @import '~@fortawesome/fontawesome-free/css/all.css';
  /* file common.scss */
  @import './assets/style/common.scss';

  .main_section {
    max-width: 100%;
    padding-top: 70px;
    min-height: 100vh;
    background-color: rgb(83, 83, 83);
  }


</style>


