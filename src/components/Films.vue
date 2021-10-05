<template>
    <section>
        <ul
        v-for="(elm, index) in films" :key="index">
            <Film :objectFilm = 'elm'></Film>
        </ul>
    </section>
</template>

<script>
import axios from 'axios';
import Film from './Film.vue';
export default {
    name : 'Films',

    data() {
        return {
            films : []
        }
    },

    props : ['infoProps'],

    components : {
        Film
    },

    created() {
    axios.get('https://api.themoviedb.org/3/search/movie', {
    params : {
        api_key : '4fb27bad81fd725bbb6d36e4ce533e33',
        query : 'Ritorno al futuro',
        language : 'it-IT'
    }
    })
    .then((res) => {
        /* console.log(res.data.results); */ //cerco i dati in console
        this.films = res.data.results;
    }
    
    );

    }
}
</script>

<style lang="scss" scoped> 

</style>