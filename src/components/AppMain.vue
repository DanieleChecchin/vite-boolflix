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
    <ul>
        <AppMainMovies />
    </ul>
    <!--SERIE TV-->
    <ul>
        <AppMainSeries />
    </ul>
</template>

<style lang="scss" scoped>
span {
    font-weight: bold;
}
</style>