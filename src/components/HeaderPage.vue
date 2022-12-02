<template>
  <header>
    <div class="navbar">
      <button
        class="title"
        @click="refreshPage()"
      >
        <h1>
          BoolFlix
        </h1>
      </button>
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
    refreshPage() {
      window.location.reload();
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
      border-radius: 1rem;

      &:active {
        animation: pulse 0.2s 1 ease-out;
      }
    }
    .title{
      background: none;
      cursor: pointer;
    }

    input, button{
      height: 25px;
    }

    @keyframes pulse {
  from {
    box-shadow:
                 0 0 0 0 rgba(129, 0, 0, 1);
  }
  to {
    box-shadow:
                 0 0 0 1em rgba(129, 0, 0, 0);
  }
  }
}
</style>
