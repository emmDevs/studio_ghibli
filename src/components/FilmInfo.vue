<template>
    <div id="film-info-container">
        <p>{{film.description}}</p>
        <p><b>Director:</b>  {{film.director}}</p>
        <p><b>Producer:</b>  {{film.producer}}</p>
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
            eventBus.$emit("show-cast", this.film.url)
        }
    }
}

</script>

<style>

</style>