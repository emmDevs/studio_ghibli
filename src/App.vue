<template>
  <div>

    <film-list :films="films"></film-list>

  </div>
</template>

<script>

import FilmList from "@/components/FilmList";

export default {
  name: 'app',
  components: {
    'film-list': FilmList,
  },
  data(){
    return{
      films: [],
      selectedFilm: null
    }
  },
  methods: {
    getFilms: function(){
      fetch("https://ghibliapi.herokuapp.com/films")
      .then(results => results.json())
      .then(data => this.films = data)
    },
  },
  mounted(){
    this.getFilms();
  }
}
</script>

<style>

</style>