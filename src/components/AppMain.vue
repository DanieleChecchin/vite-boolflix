<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    },
    computed: {
        langFlag() {
            switch (this.film.original_language) {
                case 'en':
                    return "./flags/flag_inghilterra.png";

                case 'it':
                    return "./flags/flag_italia.jpg";

                case 'fr':
                    return "./flags/flag_francia.png";

                case 'pt':
                    return "./flags/flag_portogallo.png";

                case 'ja':
                    return "./flags/flag_giappone.png";

                case 'de':
                    return "./flags/flag_germany.jpg";

                case 'es':
                    return "./flags/flag_spagna.png";

                default:
                    return "./flags/flag_sconosciuta.jpg"
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
            <span>Lingua originale:</span> {{ film.original_language }} <br>
            <span>Voto:</span> {{ film.vote_average }}
        </li>
    </ul>
</template>

<style lang="scss" scoped>
span {
    font-weight: bold;
}
</style>