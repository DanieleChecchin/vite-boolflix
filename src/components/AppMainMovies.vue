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
                return `/src/assets/${lang}.png`;
            } else {
                return '/src/assets/unknown.png';
            }

        },
        getImage(path) {
            return `https://image.tmdb.org/t/p/w200/${path}`;
        },
        ratingStar(vote) {
            return Math.ceil(`${vote}` / 2);
        },

    },
    computed: {
        currentStars() {
            return this.ratingStar;
        }
    }
}
</script>

<template>

    <li v-for="film in store.filmList">
        <img :src="getImage(film.poster_path)" alt="cover-image">
        <span>Titolo del film:</span> {{ film.title }} <br>
        <span>Titolo originiale del film:</span> {{ film.original_title }} <br>
        <span>Lingua originale:</span> <img :src="getFlagImage(film.original_language)" alt="flag"><br>
        <span>Voto:</span> {{ ratingStar(film.vote_average) }}
    </li>

    <!--<i class="fa-solid fa-star"></i>-->

</template>

<style scoped lang="scss">
i {
    color: darkgoldenrod;
}
</style>