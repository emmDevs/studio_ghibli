<template>
    <div id="film-info-container">
        <p>{{film.description}}</p>
        <p>Director:  {{film.director}}</p>
        <p>Producer:  {{film.producer}}</p>
        <button v-on:click="showCast">Show Cast</button>
    </div>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
    name: 'film-info',
    props: ["film", "people"],
    methods: {
        showCast: function(){
            eventBus.$emit("show-cast", this.film)
        }
    }
}

</script>

<style>

</style>