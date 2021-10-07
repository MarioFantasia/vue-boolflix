<template>
    <header class="flex">
        <div class="logo flex">
            <div>BOOLFLIX</div>
        </div>
        <div class="search flex">
            <div>
                <input type="text" name="" id="" placeholder="Cerca film o serie TV"
                v-model="searchItem">
            </div>
            <div>
                <button @click.prevent="$emit('search', searchItem)">Cerca</button>
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
        padding: 10px;
        justify-content: space-between;
        background-color: black;
        opacity: 0.8;
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