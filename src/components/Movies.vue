<template>
    <section class="container">
        <div v-for="movie in movieList">
        <p>{{ movie.Title }}</p>
        <img :src="movie.Poster === 'N/A' ? 'https://placehold.co/250x350/png' : movie.Poster " alt="photo" />
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

<style scoped lang="scss">
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
    padding: 2rem 4rem;

    div {

        img {
            width: 250px;
            height: 350px;
        }
    }
}

</style>