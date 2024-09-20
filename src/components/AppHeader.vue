<script>
import AppHeaderSearch from './AppHeaderSearch.vue';



export default {
    data() {
        return {

        }
    },
    methods: {
        getMovies() {
            console.log("L'evento è arrivato al componente parent")
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