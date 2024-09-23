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

}
</script>

<template>
    <!--FILM-->
    <h1 class="mb-3"> <span>Film trovati per: </span> {{ store.inputField.toUpperCase() }}</h1>
    <ul>
        <AppMainMovies />
    </ul>
    <!--SERIE TV-->
    <h1 class="mb-3"> <span>Serie TV trovate per: </span> {{ store.inputField.toUpperCase() }}</h1>
    <ul>
        <AppMainSeries />
    </ul>
</template>

<style lang="scss" scoped>
span {
    font-weight: bold;
}
</style>