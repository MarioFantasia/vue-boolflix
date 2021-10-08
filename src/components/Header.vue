<template>
    <header class="flex">
        <!-- logo -->
        <div class="logo flex">
            <div>BOOLFLIX</div>
        </div>
        <!-- ricerca elementi -->
        <div class="search flex">
            <div>
                <input type="text" name="" id="" placeholder="Cerca film o serie TV"
                v-model="searchItem"
                @keyup.enter="$emit('search', searchItem)"> <!-- rimanda ad App.vue -->
            </div>
            <div>
                <button
                @click.prevent="$emit('search', searchItem)">Cerca</button> <!-- rimanda ad App.vue -->
            </div>
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

    header {
        width: 100%;
        height: 70px;
        padding: 10px;
        position: fixed;
        justify-content: space-between;
        background-color: black;
        opacity: 0.8;
        z-index: 1;

        .logo {
            font-size: 30px;
            font-weight: 800;
            color: red;
        }
        
        .search {
            div {
                margin: auto 0;
            }

            input {
                margin-right: 5px;
                outline: none;
            }
        }
    }
</style>