<template>
    <div class="error">
        {{ message }}
    </div>
</template>

<script>
export default {
    name: "ErrorMessage",
    props: {
        message: String,
    }
}
</script>

<style scoped lang="scss">
.error {
    margin-top: 18rem;
    text-align: center;
    color: darkred;
    font-size: 1.15rem;
    font-weight: bold;
}
</style>