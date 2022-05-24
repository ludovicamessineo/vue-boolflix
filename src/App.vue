<template>
  <div id="app">
   <AppHeader @startSearch="search"/>
   <AppMain :movies="movieList" />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      movieList: []
    }
  },
  methods: {
    search(searchMovie) {
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=3497e14d9b438ed1a006312caa811e29&query=" + searchMovie)
      .then(resp => {
        this.movieList = resp.data.results
      })
    }
  }
}
</script>

<style lang="scss">
@import "./style/common.scss";
</style>
