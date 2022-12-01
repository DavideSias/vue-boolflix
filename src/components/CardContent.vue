<template>
  <div>
    <div class="card p-1">
      <img
        :src="apiImg + imgUrl"
        :alt="title"
      >
      <p>{{ title }}</p>
      <p>{{ originalTitle }}</p>
      <p> <lang-flag :iso="originalLanguage" /> </p>
      <p class="text-warning">
        <font-awesome-icon
          v-for="star in vote"
          :key="getRandomNumber(star)"
          icon="fa-solid fa-star"
        />
        <font-awesome-icon
          v-for="regular_star in (5 - vote)"
          :key="getRandomNumber(regular_star)"
          icon="fa-regular fa-star"
        />
      </p>
    </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'CardContent',
  components: {
    LangFlag,
  },
  props: {
    imgUrl: String,
    title: String,
    originalTitle: String,
    originalLanguage: String,
    vote: Number,
  },
  data() {
    return {
      apiImg: 'https://image.tmdb.org/t/p/w342',
    };
  },
  methods: {
    getRandomNumber(number) {
      return Math.random() * number;
    },
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
