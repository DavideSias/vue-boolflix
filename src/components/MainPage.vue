<template>
  <main>
    <film-page
      :get-string="getString"
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
  computed: {
    getString() {
      let getString = '';
      getString = this.searchedString;
      return getString;
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
