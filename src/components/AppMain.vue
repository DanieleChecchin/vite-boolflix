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
            if (['de', 'en', 'es', 'fr', 'it', 'ja', 'pt'].includes(lang)) {
                return `/src/assets/${lang}.png`
            } else {
                return '/src/assets/unknown.png'
            }

        }
    }


}
</script>

<template>

    <h1 class="mb-3">{{ store.inputField.toUpperCase() }}</h1>
    <ul>
        <li v-for="film in store.filmList">
            <span>Titolo del film:</span> {{ film.title }} <br>
            <span>Titolo originiale del film:</span> {{ film.original_title }} <br>
            <span>Lingua originale:</span> <img :src="getFlagImage(film.original_language)" alt="flag"><br>
            <span>Voto:</span> {{ film.vote_average }}
        </li>
    </ul>
</template>

<style lang="scss" scoped>
span {
    font-weight: bold;
}
</style>