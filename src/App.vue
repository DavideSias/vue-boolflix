<template>
  <div id="app">
    <header-page @search="getString" />
    <main-page :searched-string="searchString" />
  </div>
</template>

<script>
import HeaderPage from './components/HeaderPage.vue';
import MainPage from './components/MainPage.vue';
// importare axios (già installato)

export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },
  data() {
    return {
      searchString: '',
    };
  },
  methods: {
    getString(valueString) {
      this.searchString = valueString;
    },
  },
};
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
