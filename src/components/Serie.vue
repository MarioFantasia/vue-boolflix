<template>
    <li>
        <h3>{{objectSerie.name}}</h3>
        <h3>{{objectSerie.original_name}}</h3>
        <img style="width:25px" :src="'https://www.unknown.nu/flags/images/' + objectSerie.original_language + '-100'" :alt="objectSerie.original_language">
        <h5>{{objectSerie.vote_average}}</h5>
    </li>
</template>

<script>
export default {
    name : 'Serie',
    props : {
        objectSerie : Object
    }
}
</script>

<style lang="scss" scoped> 

</style>