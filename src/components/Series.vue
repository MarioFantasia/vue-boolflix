<template>
        <section>
        <div class="container">
            <h2 class="typeOfItem" v-if="this.serieFilter!= false">SERIES</h2>
            <div class="row row-cols-lg-5">
                <div class="col-sm-12 col-md-6 col-lg"
                v-for="(elm, index) in serieFilter" :key="index">
                    <Serie :objectSerie = 'elm'></Serie>
                </div>
            </div>
        </div>
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

    props : ['propsSerie'],

    components : {
        Serie
    },

     watch : { //resto in ascolto per intercettare la variazione del valore da dare alla query
        propsSerie : function() {
            /* console.log(this.propsSerie); */
            axios.get('https://api.themoviedb.org/3/search/tv', {
                params : {
                    api_key : '4fb27bad81fd725bbb6d36e4ce533e33',
                    query : this.propsSerie,
                    language : 'it-IT'
                }
            })
            .then((res)=> {
                this.series = res.data.results;
            });
        }
        
    },

    computed : {
        serieFilter() {
            const serieFiltered = this.series.filter(
                (elm) => {
                    if( this.propsSerie == '' ) {
                        return false;

                    } else if( elm.name.toLowerCase().includes(this.propsSerie.toLowerCase()) ) {
                        return true;
                    }
                }
            )
            return serieFiltered;
        }
    }
}
</script>

<style lang="scss" scoped> 

</style>