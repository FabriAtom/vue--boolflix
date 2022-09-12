<template>
    <div class="search">
        <h1 class="title">
            Boolflix
        </h1>
        <input type="text" placeholder="Cerca il tuo film">

    </div>

</template>

<script>
    import axios from 'axios'
    export default {
    name: 'SearchBar',
    }

</script>

<style>
    .search{
        max-height: 80px;
        max-width: 100%;
        display: flex;
        background-color: black;
    }

    .title{
        color: red;
        font-size: medium;
        justify-content: start;
        align-items: center;

    }
</style>