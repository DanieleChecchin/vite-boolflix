<script>
import AppHeaderSearch from './AppHeaderSearch.vue';
import { store } from '../store';



export default {
    data() {
        return {
            store
        }
    },
    methods: {
        getMovies() {
            console.log(store.inputField)
        }
    },
    components: {
        AppHeaderSearch
    }
}
</script>

<template>
    <h1>AppHeader</h1>
    <AppHeaderSearch @search-movies="getMovies" />
</template>

<style lang="scss" scoped></style>