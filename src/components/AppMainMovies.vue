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
            return `https://image.tmdb.org/t/p/w200/${path}`
        }
    }
}
</script>

<template>

    <li v-for="film in store.filmList"> <!--film.poster_path-->
        <img :src="getImage(film.poster_path)" alt="cover-image">
        <span>Titolo del film:</span> {{ film.title }} <br>
        <span>Titolo originiale del film:</span> {{ film.original_title }} <br>
        <span>Lingua originale:</span> <img :src="getFlagImage(film.original_language)" alt="flag"><br>
        <span>Voto:</span> {{ film.vote_average }}
    </li>

</template>

<style scoped lang="scss"></style>