<template>
        <div class="card">
        <div class="poster">
            <img v-if="objectSerie.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + objectSerie.poster_path" alt="Img">
            <img v-else src="../assets/img/imageNoPresent.png" alt="Img">
        </div>

            <!-- <div class="title">
                <h3>{{objectSerie.name}</h3>
                <h3>{{objectSerie.original_name}}</h3>
            </div>
            
            <div class="language">
                <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectSerie.original_language + '-100'" :alt="objectFilm.original_language">
            </div>
            
            <div class="votes">
                
                <span>
                    <i v-for="gold in this.goldVote" :key="gold" class="fas fa-star" style="color:yellow"></i>
                </span>
                <span>
                    <i v-for="empty in this.emptyVote" :key="empty" class="far fa-star"></i> 
                </span>
            </div> -->
    </div>
</template>
<script>

export default {
    name : 'Serie',
        data() {
        return {
            goldVote : Math.round(this.objectSerie.vote_average/2),
            emptyVote : Math.round(5 - this.objectSerie.vote_average/2)
        }
    },
    props : {
        objectSerie : Object
    },
}
</script>

<style lang="scss" scoped> 
    .card {
        margin-bottom: 10px;
    }

    .poster {
        border: 2px solid white;
    }
    img {
        margin: 0;
        width: 100%;
        height: 350px;
    }
</style>