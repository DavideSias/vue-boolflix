<template>
  <div class="mt-5">
    <h2
      v-if="arrSeries.length"
      class="mb-3"
    >
      Serie TV
    </h2>
    <div class="row row-cols-4 g-2">
      <card-content
        v-for="series in arrSeries"
        :key="series.id"
        :title="series.name"
        :original-title="series.original_name"
        :original-language="series.original_language"
        :vote="series.vote_average"
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
