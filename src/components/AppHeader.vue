<script>
import AppHeaderSearch from './AppHeaderSearch.vue';
import { store } from '../store';
import axios from 'axios';



export default {
    data() {
        return {
            store,
            apiFilmURL: 'https://api.themoviedb.org/3/search/movie?api_key=967fcf2183704fd17a1c1d259d98665a&',
            apiSeriesURL: 'https://api.themoviedb.org/3/search/tv?api_key=967fcf2183704fd17a1c1d259d98665a&'
        }
    },
    methods: {



        getMovies() {
            //Chiamata API Film
            axios.get(this.apiFilmURL, {
                params: {
                    query: store.inputField
                }
            })
                .then((response) => {
                    console.log(response.data);
                    store.filmList = response.data.results;
                });
        },
        getSeries() {

            //Chiamata API Serie
            axios.get(this.apiSeriesURL, {
                params: {
                    query: store.inputField
                }
            })
                .then((response) => {
                    console.log(response.data);
                    store.seriesList = response.data.results;
                });
        },

        getsearchMovAndSer() {  //Entrambi i metodi racchiusi in un unico metodo che passo all'evento
            this.getMovies();
            this.getSeries();
        },

    },
    components: {
        AppHeaderSearch
    }
}
</script>

<template>
    <div class="header bg-black d-flex justify-content-between align-items-center px-3 mb-5">
        <h1 class="text-danger">BOOLFLIX</h1>
        <AppHeaderSearch @searchMovies&Series="getsearchMovAndSer" />
    </div>
</template>

<style lang="scss" scoped></style>