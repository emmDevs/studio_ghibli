<template>
    <div class="film-list-item">
        <h1 class="title">{{film.title}}</h1>
        <!-- <film-image :film="film"></film-image> -->
        <button class="show-more" v-on:click="displayInfo">Show More</button>
    </div>
</template>

<script>
import { eventBus } from "@/main.js"

export default {
    name: 'film-list-item',
    props: ['film'],
    methods: {
        displayInfo: function(){
            eventBus.$emit("film-selected", this.film)
        }
    }
}
</script>

<style>
.film-list-item{
    box-sizing:border-box;
    border: 1px solid;
    display: flex;
    /* justify-content: center; */ 
}

.show-more{
    padding-top: 0;
    margin-top: 0;
}


</style>