<template>
  <div>
    <ul>
      <li>{{ title }}</li>
      <li>{{ originalTitle }}</li>
      <li>{{ originalLanguage }}</li>
      <li>{{ vote }}</li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'CardContent',
  props: {
    title: String,
    originalTitle: String,
    originalLanguage: String,
    vote: Number,
  },
};
</script>

<style lang="scss" scoped>

</style>
