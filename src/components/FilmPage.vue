<template>
  <div>
    {{ ( 'ricerca in filmPage' + ' ' + getString) }}
    <card-content :film-string="getString" />
  </div>
</template>

<script>
import CardContent from './CardContent.vue';

export default {
  name: 'FilmPage',
  components: { CardContent },
  props: {
    getString: String,
  },
};
</script>

<style lang="scss" scoped>
</style>
