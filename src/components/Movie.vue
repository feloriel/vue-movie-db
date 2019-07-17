<template>
  <img :src="moviePosterPath" :alt="movie.title" />
</template>

<script>
export default {
  props: ['movie'],
  computed: {
    moviePosterPath: function () {
      return `http://image.tmdb.org/t/p/w185${this.movie.poster_path}`;
    }
  }
}
</script>

<style lang="scss" scoped>

</style>