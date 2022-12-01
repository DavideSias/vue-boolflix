<template>
  <div>
    <h2
      v-if="arrSeries.length"
    >
      TV Series
    </h2>
    <div class="flex-container">
      <card-content
        v-for="series in arrSeries"
        :key="series.id"
        :img-url="series.poster_path"
        :title="series.name"
        :original-title="series.original_name"
        :original-language="series.original_language"
        :vote="Math.round(series.vote_average / 2)"
        :overview="series.overview"
        class="card"
      />
    </div>
  </div>
</template>

<script>
import CardContent from './CardContent.vue';

export default {
  name: 'SeriesPage',
  components: { CardContent },
  props: {
    arrSeries: Array,
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
