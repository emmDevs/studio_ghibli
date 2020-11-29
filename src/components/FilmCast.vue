<template>
    <div class="cast-list">

        <film-cast-item v-for="(person, index) in selectedFilmCast" :selectedFilmCast="selectedFilmCast" :key="index"></film-cast-item>
        

    </div>
</template>

<script>
import FilmCastItem from "@/components/FilmCastItem";


export default {
    name: 'film-cast',
    props: ["selectedFilmCast"],
    components: {
        'film-cast-item': FilmCastItem
    },
}
</script>

<style>

</style>