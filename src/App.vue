<template>

  <div id="app">
    <Header @search="searchItem"></Header>
    <!-- sezione principale con i risultati della ricerca -->
    <section class="main_section fel">
      <Films :propsFilm="takeFilm"></Films> <!-- manda il props a Films.vue -->
      <Series :propsSerie="takeSerie"></Series> <!-- manda il props a Series.vue -->
    </section>

  </div>

</template>

<script>
/* importazione componenti */
import Header from './components/Header.vue';
import Films from './components/Films.vue'; 
import Series from './components/Series.vue'

export default {
    /* componenti importati */
    components : {
      Header,
      Films,
      Series
    },
    /* dati (this) in App.vue */
    data() {
      return {
        takeFilm : "", /* elemento del props da mandare a Films.vue */
        takeSerie : "" /* elemento del props da mandare a Series.vue */
      }
    },
    /* funzioni */
    methods : {
      searchItem(item) { /* funzione che prende il valore inserito nel imput search di Header.vue e lo inserisce nei valori dei props da mandare ai file figli di App */
        this.takeFilm = item; 
        this.takeSerie = item; /* item prende il valore della ricerca dell'input */
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


