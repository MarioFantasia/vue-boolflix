<template>
    <section>
    <ul
    v-for="(elm, index) in series" :key="index">
        <Serie :objectSerie = 'elm'></Serie>
    </ul>
    </section>
</template>

<script>

import axios from 'axios';
import Serie from './Serie.vue'
export default {
    name : 'Series',
    data() {
        return {
            series : []
        }
    },
    components : {
        Serie
    },

    created() {
        axios.get('https://api.themoviedb.org/3/search/tv', {
            params : {
                api_key : '4fb27bad81fd725bbb6d36e4ce533e33',
                query : 'big',
                language : 'it-IT'
            }
        })
        .then((res) => {
            this.series = res.data.results;
        })
    }
}
</script>

<style lang="scss" scoped> 

</style>