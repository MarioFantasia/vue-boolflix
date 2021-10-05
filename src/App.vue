<template>
  <div id="app">
    <Header></Header>
    <Films></Films>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Films from './components/Films.vue'; 
export default {
    components : {
      Header,
      Films
    },
    created() {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params : {
          api_key : '4fb27bad81fd725bbb6d36e4ce533e33',
          query : 'Ritorno al futuro',
          language : 'it-IT'
        }
      })
      .then(function(res) {
        console.log(res.data.results); //cerco i dati in console
      }
      
      );

    }
}
</script>

<style lang="scss">

</style>


