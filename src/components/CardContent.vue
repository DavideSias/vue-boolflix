<template>
  <div>
    {{ ( 'ricerca in cardContent' + ' ' + filmString) }}
  </div>
</template>

<script>
export default {
  name: 'CardContent',
  props: {
    filmString: String,
  },
};
</script>

<style lang="scss" scoped>

</style>
