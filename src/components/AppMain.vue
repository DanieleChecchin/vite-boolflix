<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h1>AppMain</h1>
    <ul>
        <li v-for="film in store.filmList">
            Titolo del film: {{ film.title }} <br>
            Titolo originiale del film: {{ film.original_title }} <br>
            Lingua originale: {{ film.original_language }} <br>
            Voto: {{ film.vote_average }}
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>