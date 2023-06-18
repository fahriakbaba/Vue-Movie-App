<template>
    <header>
        <img src="https://avatars.githubusercontent.com/u/6128107?s=280&v=4" alt="vue-photo">
        <h6>Vue Movie App</h6>
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
    justify-content: flex-start;
    align-items: center;
    padding: 1.25rem;

    img {
        width: 45px;
    }

    h6 {
        font-size: 1.05rem;
    }
}
</style>