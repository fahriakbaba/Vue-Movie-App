<template>
    <section class="container">
        <div v-for="movie in movieList">
            <img :src="movie.Poster === 'N/A' ? 'https://placehold.co/250x350/png' : movie.Poster" alt="photo" />
            <p>{{ movie.Title }}</p>
            <span>{{ movie.Year }}</span>
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
        box-shadow: .5px .5px 5px gainsboro;
        width: 250px;
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        border-radius: 8px;
        transition: box-shadow .5s, transform .5s;

        &:hover {
            box-shadow: 1px 1px 5px gray;
            transform: scale(1.05);
        }

        img {
            width: 250px;
            height: 350px;
            border-radius: 8px 8px 0 0;
        }

        p{
            font-size: 1rem;
            font-weight: bold;
            margin: .5rem auto;
        }

        span {
            font-size: .75rem;
        }
    }
}
</style>