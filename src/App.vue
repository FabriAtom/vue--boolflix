<template>
  <div id="app">
    <SearchBar @onResponse="setMovies" />
    <ul>
      <CardMovie v-for="movie in movies" :key="movie.id" :movie="movie" />
    </ul>
  </div>
</template>



<script>
import CardMovie from './components/CardMovie.vue'
import SearchBar from './components/SearchBar.vue'

export default {
  name: 'App',
  data() {
      return {
        original_movies:[],
        api_key:"c35650324876c9a570dd037e052ea8e9",
        query:'',
        BASE_URI:"https://api.themoviedb.org/3",
        posterBaseUri:'https://blablabla/'
      };
  },
  computed: {
    movies() {
      return this.original_movies.map((el) => {
        const newMovie = {
          id: el.id,
          title: el.title,
          original_title: el.original_title,
          lang: el.original_language,
          flag: '',
          poster: `${this.posterBaseUri}w342${el.poster_path}`,
          vote: Math.round(el.vote_average / 2)
        }

        return newMovie
      })
    }
  },
  methods: {
    setMovies(movies) {
      this.movies = movies
    },
  },
  components: {
    SearchBar,
    CardMovie
  }
}
</script>



<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

