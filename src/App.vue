<template>
  <Header @search-movie="getMovie" />
  <div v-show="!isLoading">
    <Movies :movieList="movieList" />
  </div>
  <div v-show="isLoading">
    <Loading />
  </div>
  <div v-show="errorMessage">
    {{ errorMessage }}
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Movies from "./components/Movies.vue";
import Loading from "./components/Loading.vue";

export default {
  name: 'App',
  components: {
    Header,
    Movies,
    Loading
  },
  data() {
    return {
      movieList: [],
      errorMessage: "",
      isLoading: false
    }
  },
  methods: {
    async getMovie(movieName) {
      this.isLoading = true;
      this.errorMessage = "";
      const res = await fetch(`http://www.omdbapi.com/?apikey=334af70c&s=${movieName}`);
      const data = await res.json();

      console.log("res: ", res);
      console.log("data: ", data);


      setTimeout(() => {
        if ((res.status === 200) && (data.Response === "True")) {
          this.movieList = data.Search;
          this.errorMessage = "";
        } else {
          this.errorMessage = data.Error;
          this.movieList = [];
        }

        this.isLoading = false;
      }, 2000)
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
