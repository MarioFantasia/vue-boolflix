<template>
    <header>
        <div class="search">
            <input type="text" name="" id="" placeholder="Cerca film o serie TV"
            v-model="searchItem">
        </div>
        <div class="button">
            <button @click.prevent="$emit('search', searchItem)">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name : 'Header',
    data() {
        return {
            searchItem : ""
        }
    }
}
</script>

<style lang="scss" scoped> 

</style>