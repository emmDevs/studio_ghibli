<template>
  <div>
    <h1>Studio Ghibli</h1>

    <film-filter-form :films="films" />

    <film-info v-if="selectedFilm" :film="selectedFilm" :people="people"></film-info>

    <film-list :films="films"></film-list>

    <film-cast v-model=getCast :selectedFilmCast="selectedFilmCast"></film-cast>

  </div>
</template>

<script>

import FilmList from "@/components/FilmList";
import FilmInfo from "@/components/FilmInfo";
import FilmCast from "@/components/FilmCast";
import FilmFilterForm from "@/components/FilmFilterForm";
import { eventBus } from "@/main.js";


export default {
  name: 'app',
  components: {
    'film-list': FilmList,
    'film-info': FilmInfo,
    'film-cast': FilmCast,
    'film-filter-form':FilmFilterForm,
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
      fetch("https://ghibliapi.herokuapp.com/people")
      .then(results => results.json())
      .then(data => this.people = data)

    },

    getCast: function(){
      for(person in people){
        for(url in films){
        if (people.films === this.films.url){
          selectedFilmCast.push(people[index])
        }
        }
      }
    }
    
    },
  mounted(){
    this.getFilms();
    this.getPeople();

    eventBus.$on('film-selected', film =>(this.selectedFilm = film));
    eventBus.$on('show-cast', film =>(this.film.url = film))
    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
  }
}

</script>

<style>

</style>