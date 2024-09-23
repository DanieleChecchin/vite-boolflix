<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    },
    methods: {
        getFlagImage(lang) {
            if (['de', 'en', 'es', 'fr', 'it', 'ja', 'pt', 'zh'].includes(lang)) {
                return `/src/assets/${lang}.png`
            } else {
                return '/src/assets/unknown.png'
            }

        },
        getImage(path) {
            return `https://image.tmdb.org/t/p/w342/${path}`
        }
    }
}

</script>

<template>

    <li v-for="series in store.seriesList">
        <img :src="getImage(series.poster_path)" alt="cover-image">
        <span>Titolo della serie:</span> {{ series.name }} <br>
        <span>Titolo originiale della serie:</span> {{ series.original_name }} <br>
        <span>Lingua originale:</span> <img :src="getFlagImage(series.original_language)" alt="flag"><br>
        <span>Voto:</span> {{ series.vote_average }}
    </li>

</template>

<style scoped lang="scss"></style>