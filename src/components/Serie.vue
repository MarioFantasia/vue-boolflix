<template>
    <li>
        <h3>{{objectSerie.name}}</h3>
        <h3>{{objectSerie.original_name}}</h3>
        <h4>{{objectSerie.original_language}}</h4>
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