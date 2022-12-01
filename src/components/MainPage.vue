<template>
  <main>
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

</style>
