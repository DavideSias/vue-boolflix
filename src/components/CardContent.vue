<template>
  <div>
    <div class="card p-1">
      <img
        :src="apiImg + imgUrl"
        :alt="title"
      >
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
    imgUrl: String,
    title: String,
    originalTitle: String,
    originalLanguage: String,
    vote: Number,
  },
  data() {
    return {
      apiImg: 'https://image.tmdb.org/t/p/w500',
    };
  },
};
</script>

<style lang="scss" scoped>
.card{
  border: none;
  height: 100%;
  p {
    margin: 0;
  }
}
</style>
