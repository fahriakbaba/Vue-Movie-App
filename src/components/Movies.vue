<template>
    <section class="container">
        <div v-for="movie in movieList">
        <p>{{ movie.Title }}</p>
        <!-- <img :src="movie.Poster" alt="photo" /> -->
        </div>
    </section>
</template>

<script>
export default {
    name: "Movies",
    props: {
        movieList: Array
    }

}
</script>

<style scoped>
.container {
    padding: 2rem 4rem;
}

</style>