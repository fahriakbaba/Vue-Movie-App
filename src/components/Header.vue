<template>
    <header>
        <div class="logo">
            <img src="https://avatars.githubusercontent.com/u/6128107?s=280&v=4" alt="vue-photo">
            <h6>Vue Movie App</h6>
        </div>
        <div class="search">
            <input type="text" />
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",

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
}
</style>