<template>
    <section>
        movies lists
        <div v-for="movie in movieList">
        <p>{{ movie.Title }}</p>
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

<style scoped></style>