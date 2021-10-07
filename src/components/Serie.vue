<template>
    <li>
        <h3>{{objectSerie.name}}</h3>
        <h3>{{objectSerie.original_name}}</h3>
        <img v-if="objectSerie.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + objectSerie.poster_path" alt="Img">
            <img v-else src="../assets/img/imageNoPresent.png" alt="Img" style="width:342px">
        <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectSerie.original_language + '-100'" :alt="objectSerie.original_language">
        <!-- <h5>{{objectSerie.vote_average}}</h5> -->
        <h5>{{this.vote}}</h5>
    </li>
</template>

<script>
export default {
    name : 'Serie',
        data() {
        return {
            vote : Math.round(this.objectSerie.vote_average/2)
        }
    },
    props : {
        objectSerie : Object
    }
}
</script>

<style lang="scss" scoped> 
    img {
        display: block;     //temporanee
        margin-bottom: 5px; 
    }
</style>