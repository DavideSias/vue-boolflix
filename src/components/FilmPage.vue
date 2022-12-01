<template>
  <div>
    <h2 v-if="arrMovies.length">
      Movies
    </h2>
    <card-content
      v-for="movie in arrMovies"
      :key="movie.id"
      :title="movie.title"
      :original-title="movie.original_title"
      :original-language="movie.original_language"
      :vote="movie.vote_average"
    />
  </div>
</template>

<script>
import CardContent from './CardContent.vue';

export default {
  name: 'FilmPage',
  components: { CardContent },
  props: {
    arrMovies: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>
