<template>
    <section>
        <div class="container">
            <h2 class="typeOfItem" v-if="this.films!=false">FILMS</h2>
            <div class="row row-cols-lg-5">
                <div class="col-sm-12 col-md-6 col-lg"
                v-for="(elm, index) in filmFilter" :key="index">
                    <Film :objectFilm = 'elm'></Film>
                </div>
            </div>
        </div>
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

    props : ['propsFilm'],

    components : {
        Film
    },

    watch : { //resto in ascolto per intercettare la variazione del valore da dare alla query
        propsFilm : function() {
            /* console.log(this.propsFilm); */
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params : {
                    api_key : '4fb27bad81fd725bbb6d36e4ce533e33',
                    query : this.propsFilm,
                    language : 'it-IT'
                }
            })
            .then((res)=> {
                this.films = res.data.results;
            });
        }
        
    },

    computed : {
        filmFilter() {
            const filmFiltered = this.films.filter(
                (elm) => {
                    if( this.propsFilm == '' ) {
                        return false;

                    } else if( elm.title.toLowerCase().includes(this.propsFilm.toLowerCase()) ) {
                        return true;
                    }
                }
            )
            return filmFiltered;
        }
    }
}
</script>

<style lang="scss" scoped> 

</style>