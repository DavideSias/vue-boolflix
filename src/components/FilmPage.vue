<template>
  <div>
    {{ ( 'ricerca in filmPage' + ' ' + getString) }}
  </div>
</template>

<script>
export default {
  name: 'FilmPage',
  props: {
    getString: String,
  },
};
</script>

<style lang="scss" scoped>

</style>
