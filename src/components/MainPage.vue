<template>
  <main class="container">
    <film-page :arr-movies="arrMovies" />
    <series-page :arr-series="arrSeries" />
  </main>
</template>

<script>
import FilmPage from '@/components/FilmPage.vue';
import SeriesPage from '@/components/SeriesPage.vue';

export default {
  name: 'MainPage',
  components: {
    FilmPage,
    SeriesPage,
  },
  props: {
    arrMovies: Array,
    arrSeries: Array,
  },
};
</script>

<style lang="scss" scoped>
 .container {
  max-width: 1000px;
  margin: 2rem auto;
 }
</style>
