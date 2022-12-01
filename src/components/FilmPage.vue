<template>
  <div>
    <h2
      v-if="arrMovies.length"
      class="mb-3"
    >
      Movies
    </h2>
    <div class="row row-cols-4 g-2">
      <card-content
        v-for="movie in arrMovies"
        :key="movie.id"
        :title="movie.title"
        :original-title="movie.original_title"
        :original-language="movie.original_language"
        :vote="movie.vote_average"
      />
    </div>
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
