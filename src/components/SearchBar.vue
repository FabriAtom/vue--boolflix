<template>
        <div class="search">
            <h1 class="title">
                Boolflix
            </h1>
            <input type="text" placeholder="Cerca il tuo film" v-model="query">
            <input type="button" value="Cerca" @click="fetchMovies">
        </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
             query: '',
             api_key:"c35650324876c9a570dd037e052ea8e9",
             BASE_URI:"https://api.themoviedb.org/3"
            }
        },
        methods: {
            fetchMovies() {
              if(this.query.trim() === '')
                 return
                //  chiamata
             axios.get(`${this.BASE_URI}/search/movie`, {
                params: {
                 api_key: this.api_key,
                 query: this.query.trim()
                }
            })
            // evento 
            .then(res => {
            console.log(res.data);
            this.$emit('onResponse', res.data.results)
            });
        }
    },
    }

</script>



<style>
    .search{
        height: 80px;
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