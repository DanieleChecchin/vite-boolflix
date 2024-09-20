<script>

import { store } from "../store.js";

export default {
    data() {
        return {
            store
        }
    },
    methods: {
        searchedInput() {
            console.log(store.inputField);
            this.$emit('searchMovies');
        }
    }

}
</script>

<template>
    <div class="input-group mb-3 w-50">
        <input type="text" class="form-control" placeholder="search for a movie.." v-model="store.inputField">
        <button class="btn btn-outline-secondary" type="button" @click="searchedInput">Search</button>
    </div>
</template>

<style lang="scss" scoped></style>