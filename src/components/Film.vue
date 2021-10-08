<template>
    <div class="card">
        <div class="poster">
            <img v-if="objectFilm.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + objectFilm.poster_path" alt="Img">
            <img v-else src="../assets/img/imageNoPresent.png" alt="Img">
        </div>
        <div class="info_card">
            <div class="title">
                <h3><span>Titolo: </span>{{objectFilm.title}}</h3>
                <h3><span>Titolo originale: </span>{{objectFilm.original_title}}</h3>
            </div>
            
            <div class="language">
                <span>Lingua: </span>
                <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectFilm.original_language + '-100'" :alt="objectFilm.original_language">
            </div>
            
            <div class="votes">
                <!-- è necessario mettere dentro a due span per non dare errore di duplicazione della chiave -->
                <span>Voto: <i v-for="gold in this.goldVote" :key="gold" class="fas fa-star" style="color:yellow"></i></span>
                <span><i v-for="empty in this.emptyVote" :key="empty" class="far fa-star"></i> </span>
            </div>

            <div class="description">
                <h5>{{objectFilm.overview}}</h5>
            </div>
        </div>
    </div>

</template>

<script>
export default {
    name : 'Film',
    data() {
        return {
            goldVote : Math.round(this.objectFilm.vote_average/2),
            emptyVote : Math.round(5 - this.objectFilm.vote_average/2)
        }
    },
    props : {
        objectFilm : Object
    }

}
</script>

<style lang="scss" scoped>
    .card {
        border: none;
        margin-bottom: 10px;
        position: relative;
    }

    .poster {

        img {
            margin: 0;
            width: 100%;
            height: 350px;
        }
    }

    .info_card {
        width: 100%;
        height: 350px;
        padding: 5px;
        background-color: gray;
        display: none;
        position: absolute;
    }

    .description {
        height: 200px;
        overflow-y: auto;
        scrollbar-width: 1px;
    }

    /* font */
    h3 {
        font-size: 15px;
        font-weight: 800;
        span {
            font-size: 16px;
            font-weight: 800;
        }
    }

    h5 {
        font-size: 10px;
    }



    /* effetti */
    .card:hover .poster {
    visibility: hidden;
    }

    .card:hover .info_card {
    display: block;
}

</style>
