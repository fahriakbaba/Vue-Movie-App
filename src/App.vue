<template>
  <Header @search-movie="getMovie" />
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: 'App',
  components: {
    Header
  },
  data() {
    return {
      movieList: [],
      errorMessage: "",
    }
  },
  methods: {
    async getMovie(movieName) {
      const res = await fetch(`http://www.omdbapi.com/?apikey=334af70c&s=${movieName}`);
      const data = await res.json();

      console.log("res: ", res);
      console.log("data: ",data);

      if ((res.status === 200) && (data.Response === "True")) {
        this.movieList = data.Search;
        this.errorMessage ="";
      } else {
        this.errorMessage= data.Error;
        this.movieList = [];
      }

    },
  },

}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Roboto', sans-serif;
}
</style>
