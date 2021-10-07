<template>
        <li>
            <h3>{{objectFilm.title}}</h3>
            <h3>{{objectFilm.original_title}}</h3>
            <img v-if="objectFilm.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + objectFilm.poster_path" alt="Img">
            <img v-else src="../assets/img/imageNoPresent.png" alt="Img" style="width:342px">
            <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectFilm.original_language + '-100'" :alt="objectFilm.original_language">
            <h5>{{objectFilm.vote_average}}</h5>
        </li>
</template>

<script>
export default {
    name : 'Film',
    props : {
        objectFilm : Object
    }
}
</script>

<style lang="scss" scoped> 
    img {
        display: block;     //temporanee
        margin-bottom: 5px; 
    }
</style>