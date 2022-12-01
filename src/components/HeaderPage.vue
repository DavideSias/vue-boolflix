<template>
  <header>
    <div class="navbar">
      <h1>BoolFlix</h1>
      <div>
        <label for="s">
          <input
            id="s"
            v-model="searchString"
            type="text"
            name="s"
            @keyup.enter="search"
          >
          <button @click="search">Search</button>
        </label>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  data() {
    return {
      searchString: '',
    };
  },
  methods: {
    search() {
      this.$emit('search', this.searchString);
      this.searchString = '';
    },
  },
};
</script>

<style lang="scss" scoped>
  .navbar{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: black;
    padding: 1rem;

    h1 {
      color: red;
      text-transform: uppercase;
    }
  }
</style>
