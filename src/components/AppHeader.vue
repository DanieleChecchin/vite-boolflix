<script>
import AppHeaderSearch from './AppHeaderSearch.vue';
import { store } from '../store';
import axios from 'axios';



export default {
    data() {
        return {
            store,
            apiURL: 'https://api.themoviedb.org/3/search/movie?api_key=967fcf2183704fd17a1c1d259d98665a&'
        }
    },
    methods: {
        getMovies() {
            //Chiamata API
            axios.get(this.apiURL, {
                params: {
                    query: store.inputField
                }
            })
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (error) {
                    console.log(error);
                });
            console.log(store.inputField)
        },


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