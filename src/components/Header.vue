<template>
    <header>
        <div class="logo">
            <img src="https://avatars.githubusercontent.com/u/6128107?s=280&v=4" alt="vue-photo">
            <h6>Vue Movie App</h6>
        </div>
        <form class="search" @submit.prevent="handleSubmit">
            <input type="text" v-bind:placeholder="placeholder" v-model="searchMovie" />
            <button type="submit" class="btn">Search</button>
        </form>
    </header>
</template>

<script>
export default {
    name: "Header",
    data() {
        return {
            searchMovie: "",
            placeholder: "Search movie you want!",
            API_key: "334af70c",  
        }
    },
    methods: {
        handleSubmit() {
            const getMovie = async (movieName) => {
                const res = await fetch(`http://www.omdbapi.com/?apikey=${this.API_key}&s=${movieName}`);
                const data = await res.json();
                console.log("data: ", data);
            }

            getMovie(this.searchMovie)

            console.log(this.searchMovie);
            this.searchMovie = "";
        }
    }
}
</script>

<style scoped lang="scss">
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: .75rem 1.5rem;
    box-shadow: .5px .5px 5px gainsboro;

    .logo {
        display: flex;
        justify-content: flex-start;
        align-items: center;

        img {
            width: 45px;
        }

        h6 {
            font-size: 1.05rem;
            color: darkgreen;
            opacity: .75;
            letter-spacing: .1px;
            word-spacing: 1px;
            margin-left: .5rem;
        }
    }

    .search {
        input {
            padding: 4px 8px;
            outline: none;
            border-radius: 3px 0 0 3px;
            border: 2px solid #41B883;
            transition: all .7s;

            &::placeholder {
                color: gray;
            }

            &:focus {
                border-color: #298f61e1;
            }
        }

        .btn {
            padding: 4px 8px;
            border-radius: 0 3px 3px 0;
            cursor: pointer;
            background-color: white;
            color: darkgreen;
            border: 2px solid #41B883;
            border-left: none;
            transition:  all .7s;
            outline: none;

            &:hover {
                background-color: darkgreen;
                color: white;
                border-color: darkgreen;
            }
        }
    }
}
</style>



<!-- const API_key = "334af70c";
`http://www.omdbapi.com/?apikey=${API_key}&s=${searchMovie}` -->