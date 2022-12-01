<template>
  <div>
    <div class="card p-1">
      <p>{{ title }}</p>
      <p>{{ originalTitle }}</p>
      <p>{{ originalLanguage }}</p>
      <p>{{ vote }}</p>
    </div>
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
.card{
  border: 1px solid black;
  border-radius: 0.5rem;
  height: 100%;

  p {
    margin: 0;
  }
}
</style>
