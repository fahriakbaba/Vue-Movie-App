<template>
  <Header @search-movie="getMovie()" />
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
    }
  },
  methods: {
    getMovie: async function(movieName) {
      
      const res = await fetch(`http://www.omdbapi.com/?apikey=334af70c&s=${movieName}`);
      const data = await res.json();
      console.log("data: ",data.Search);

      if(res.status === 200) {
      this.movieList = data.Search;
      console.log("movielist",this.movieList);
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
