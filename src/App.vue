<template>
  <div id="app">
    <header-page @search="getString" />
    <main-page
      :arr-movies="arrMovies"
      :arr-series="arrSeries"
    />
  </div>
</template>

<script>
import axios from 'axios';
import HeaderPage from './components/HeaderPage.vue';
import MainPage from './components/MainPage.vue';

export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },
  data() {
    return {
      searchString: '',
      urlApi: 'https://api.themoviedb.org/3',
      apiKey: 'e7c1491d70bba2fc5602ee6afc0632a2',
      resultIta: 'it-IT',
      arrMovies: [],
      arrSeries: [],
    };
  },
  methods: {
    getString(valueString) {
      axios.get(`${this.urlApi}/search/movie`, {
        params: {
          api_key: this.apiKey,
          query: valueString,
          language: this.resultIta,
        },
      })
        .then((responseAxios) => {
          this.arrMovies = responseAxios.data.results;
          console.log(this.arrMovies);
        });

      axios.get(`${this.urlApi}/search/tv`, {
        params: {
          api_key: this.apiKey,
          query: valueString,
          language: this.resultIta,
        },
      })
        .then((responseAxios) => {
          this.arrSeries = responseAxios.data.results;
          console.log(this.arrMovies);
        });
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  font-family: 'Roboto', sans-serif;
}
</style>
