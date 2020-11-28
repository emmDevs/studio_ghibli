<template>
    <div class="film-list">
        <film-list-item v-for="(film, index) in films" :film="film" :key="index"> <img v-bind:src="`../assets/${film.title}`"></film-list-item>
    </div>

</template>

<script>

import FilmListItem from "@/components/FilmListItem";

export default {
    name: 'film-list',
    props: ['films'],
    components: {
        'film-list-item': FilmListItem
    }

}
</script>

<style>
.film-list{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    
}
</style>