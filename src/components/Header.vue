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
            if(!this.searchMovie) {
                alert("Please, enter a valid movie search name!");
            }

            this.$emit("search-movie", this.searchMovie)
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
    padding: 1.5rem 3rem;
    box-shadow: .5px .5px 5px gainsboro;

    .logo {
        display: flex;
        justify-content: flex-start;
        align-items: center;

        img {
            width: 45px;
        }

        h6 {
            font-size: 1.25rem;
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
            background-color: #41B883;
            color: white;
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

@media (max-width: 480px) {
    header {
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: .5rem;
    }
}
</style>



<!-- const API_key = "334af70c";
`http://www.omdbapi.com/?apikey=${API_key}&s=${searchMovie}` -->