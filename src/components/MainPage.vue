<template>
  <main>
    <film-page
      :main-string="searchedString"
    />
  </main>
</template>

<script>
import FilmPage from '@/components/FilmPage.vue';

export default {
  name: 'MainPage',
  components: {
    FilmPage,
  },
  props: {
    searchedString: String,
  },
};
</script>

<style lang="scss" scoped>

</style>
