<template>
    <header>
        <div class="search">
            <input type="text" name="" id="" placeholder="Cerca film"
            v-model="searchFilm">
        </div>
        <div class="button">
            <button @click.prevent="$emit('search', searchFilm)">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name : 'Header',
    data() {
        return {
            searchFilm : ""
        }
    }
}
</script>

<style lang="scss" scoped> 

</style>