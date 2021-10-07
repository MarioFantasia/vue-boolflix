<template>
    <li>
        <h3>{{objectSerie.name}}</h3>
        <h3>{{objectSerie.original_name}}</h3>
        <img v-if="objectSerie.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + objectSerie.poster_path" alt="Img">
            <img v-else src="../assets/img/imageNoPresent.png" alt="Img" style="width:342px">
        <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectSerie.original_language + '-100'" :alt="objectSerie.original_language">
        <!-- <h5>{{objectSerie.vote_average}}</h5> -->
        <h5>{{this.goldVote}}</h5>
        <span>
            <i v-for="gold in this.goldVote" :key="gold" class="fas fa-star" style="color:yellow"></i>
        </span>
        <span>
            <i v-for="empty in this.emptyVote" :key="empty" class="far fa-star"></i> 
        </span>
    </li>
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
    img {
        display: block;     //temporanee
        margin-bottom: 5px; 
    }
</style>