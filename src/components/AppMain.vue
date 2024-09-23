<script>
import { store } from '../store';
import AppMainMovies from './AppMainMovies.vue';
import AppMainSeries from './AppMainSeries.vue';

export default {
    data() {
        return {
            store
        }
    },
    components: {
        AppMainMovies,
        AppMainSeries
    },
    methods: {
        getFlagImage(lang) {
            if (['de', 'en', 'es', 'fr', 'it', 'ja', 'pt', 'zh'].includes(lang)) {
                return `/src/assets/${lang}.png`
            } else {
                return '/src/assets/unknown.png'
            }

        }
    }
}
</script>

<template>
    <!--FILM-->
    <h1 class="mb-3"> <span>Film trovati per: </span> {{ store.inputField.toUpperCase() }}</h1>
    <ul>
        <li v-for="film in store.filmList">
            <span>Titolo del film:</span> {{ film.title }} <br>
            <span>Titolo originiale del film:</span> {{ film.original_title }} <br>
            <span>Lingua originale:</span> <img :src="getFlagImage(film.original_language)" alt="flag"><br>
            <span>Voto:</span> {{ film.vote_average }}
        </li>
    </ul>
    <!--SERIE TV-->
    <h1 class="mb-3"> <span>Serie TV trovate per: </span> {{ store.inputField.toUpperCase() }}</h1>
    <ul>
        <li v-for="series in store.seriesList">
            <span>Titolo della serie:</span> {{ series.name }} <br>
            <span>Titolo originiale della serie:</span> {{ series.original_name }} <br>
            <span>Lingua originale:</span> <img :src="getFlagImage(series.original_language)" alt="flag"><br>
            <span>Voto:</span> {{ series.vote_average }}
        </li>
    </ul>
</template>

<style lang="scss" scoped>
span {
    font-weight: bold;
}
</style>