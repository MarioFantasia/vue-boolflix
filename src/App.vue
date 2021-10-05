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
      axios.get('https://api.themoviedb.org/3/search/movie'), {
        params : {
          
        }
      }
    }
}
</script>

<style lang="scss">

</style>
