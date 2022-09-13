<template>
    <li>
        <h3>{{ movie.title }}</h3>
        <p>{{ movie.original_title }}</p>
        <p>{{ movie.lang }}</p>
        <p>{{ movie.vote }}</p>
        <p>{{ movie.poster }}</p>
        <p>{{ movie.flag }}</p>

    </li>
</template>

<script>
    export default{
        props:{
            movie: {
                type: Object,
                required: true
            }
        }
    }

</script>

<style lang="scss" scoped>

</style>