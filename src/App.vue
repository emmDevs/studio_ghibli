<template>
  <div>

    <film-list :films="films"></film-list>

    <film-info v-if="selectedFilm" :film="selectedFilm" :people="people"></film-info>

    <film-cast :people="people"></film-cast>

  </div>
</template>

<script>

import FilmList from "@/components/FilmList";
import FilmInfo from "@/components/FilmInfo";
import FilmCast from "@/components/FilmCast";
import { eventBus } from "@/main.js";


export default {
  name: 'app',
  components: {
    'film-list': FilmList,
    'film-info': FilmInfo,
    'film-cast': FilmCast,
  },
  data(){
    return{
      films: [],
      selectedFilm: null,
      people: [],
      selectedFilmCast: [],
    }
  },
  methods: {
    getFilms: function(){
      fetch("https://ghibliapi.herokuapp.com/films")
      .then(results => results.json())
      .then(data => this.films = data)
    },
    getPeople: function(){
      fetch(this.film.people)
      .then(results => results.json())
      .then(data => this.people = data)

    },
    
    },
  mounted(){
    this.getFilms();

    eventBus.$on('film-selected', film =>(this.selectedFilm = film));
    eventBus.$on('show-cast', film =>(this.selectedFilm = film))
  }
}
</script>

<style>

</style>