<template>
  <div>
    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img
            :src="apiImg + imgUrl"
            :alt="title"
          >
        </div>
        <div class="flip-card-back">
          <p><span>Titolo:</span> {{ title }}</p>
          <p><span>Titolo Originale:</span> {{ originalTitle }}</p>
          <p> <lang-flag :iso="originalLanguage" /> </p>
          <p>
            <span>Voto: </span>
            <font-awesome-icon
              v-for="star in vote"
              :key="getRandomNumber(star)"
              icon="fa-solid fa-star"
              class="icon"
            />
            <font-awesome-icon
              v-for="regular_star in (5 - vote)"
              :key="getRandomNumber(regular_star)"
              icon="fa-regular fa-star"
              class="icon"
            />
          </p>
          <p>{{ overview }}</p>
        </div>
      </div>
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
    overview: String,
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
.flip-card {
  background-color: transparent;
  width: 300px;
  aspect-ratio: 1 / 1.5;
  perspective: 1000px;

}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  border-radius: 10px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px, rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
}

.flip-card-front {
  background-color: transparent;
  color: black;
  img{
    width: 100%;
    border-radius: 10px;
  }
}

.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
  padding: 1rem;
  text-overflow: hidden; // TODO: sistemare l'overflow del testo

  p{
    margin: 0.5rem 0;

    span{
      font-weight: 700;
    }
  }

}

.icon{
  color: rgb(197, 197, 12);
}

</style>
