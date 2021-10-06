<template>
        <li>
            <h3>{{objectFilm.title}}</h3>
            <h3>{{objectFilm.original_title}}</h3>
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

</style>