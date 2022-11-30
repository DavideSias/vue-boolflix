<template>
  <div>
    {{ ( 'ricerca in filmPage' + ' ' + mainString) }}
    <card-content :film-string="mainString" />
  </div>
</template>

<script>
import CardContent from './CardContent.vue';

export default {
  name: 'FilmPage',
  components: { CardContent },
  props: {
    mainString: String,
  },
};
</script>

<style lang="scss" scoped>
</style>
