<template>
  <ul>
    <li v-for="movie in movies" :key="movie.id">
      <Movie :movie="movie" />
    </li>
  </ul>
</template>

<script>
import Movie from './Movie.vue'
export default {
  name: "MoviesList",
  data() {
    return {
      movies: []
    }
  },
  beforeCreate: function() {
    console.log('before create');
  },
  created: function() {
    console.log('created');
    this.fetchData();
  },
  beforeMount: function() {
    console.log('before mount');
  },
  mounted: function() {
    console.log('mounted');
  },
  beforeUpdate: function() {
    console.log('before update');
  },
  updated: function() {
    console.log('updated');
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          'https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=41ec87053aad3d57b5bf94fdf89f4086'
        );
        const movies = await res.json();
        this.movies = movies.results;
      } catch (e) {
        console.log(e);
      }
    }
  },
  components: {
    Movie
  }
};
</script>

<style scoped>
ul {
  display: grid;
  list-style: none;
  padding: 1rem;
  margin: 0;
  grid-row-gap: 1rem;
  grid-template-columns: repeat(6, 1fr);
}
</style>