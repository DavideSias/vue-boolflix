<template>
  <div>
    <h2
      v-if="arrMovies.length"
    >
      Movies
    </h2>
    <div class="flex-container">
      <card-content
        v-for="movie in arrMovies"
        :key="movie.id"
        :img-url="movie.poster_path"
        :title="movie.title"
        :original-title="movie.original_title"
        :original-language="movie.original_language"
        :vote="Math.round(movie.vote_average / 2)"
        :overview="movie.overview"
        class="card"
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
h2{
  margin: 2rem 0;
}
.flex-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 2rem;
}

.card{
  cursor: pointer;
}
</style>
