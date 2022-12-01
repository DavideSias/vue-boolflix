<template>
  <div class="mt-5">
    <h2
      v-if="arrSeries.length"
      class="mb-3"
    >
      Serie TV
    </h2>
    <div class="row row-cols-4 g-3">
      <card-content
        v-for="series in arrSeries"
        :key="series.id"
        :img-url="series.poster_path"
        :title="series.name"
        :original-title="series.original_name"
        :original-language="series.original_language"
        :vote="Math.round(series.vote_average / 2)"
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

</style>
