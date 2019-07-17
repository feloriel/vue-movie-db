<template>
  <div id="app" v-if="status === 'Ready'">
    <Header :title="title" />
    <MoviesList />
  </div>
  <div v-else-if="status === 'Loading'">
    Loading
  </div>
  <div v-else>
    Error
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MoviesList from './components/MoviesList.vue';

export default {
  name: 'app',
  data() {
    return {
      hello: 'Hello World',
      title: 'Vue Movie DB',
      isTrue: true,
      status: 'Ready'
    };
  },
  components: {
    Header,
    MoviesList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
}
</style>
