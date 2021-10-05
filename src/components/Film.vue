<template>
        <li>
            <h3>{{objectFilm.title}}</h3>
            <h3>{{objectFilm.original_title}}</h3>
            <h4>{{objectFilm.original_language}}</h4>
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