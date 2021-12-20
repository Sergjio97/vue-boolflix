<template>
  <main>
      <nav>
          <input type="text" placeholder="inserisci il titolo" v-model="inputValue">
          <button @click="searchFilm">Cerca</button>
          <div class="films-info" v-for="(film, index) in filmList" :key="index">
              <h3>Titolo: {{film.title}}</h3>
              <h3>Titolo Originale: {{film.original_title}}</h3>
              <h3>Lingua: {{film.original_language}}</h3>
              <h3>Valutazione: {{film.vote_average}}</h3>
          </div>
      </nav>
  </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data() {
        return {
            inputValue: '',
            filmList: []
        }
    },
    methods: {
        searchFilm() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                api_key: 'eebcf7c938b9bfe34e05762eae2bec88',
                query: this.inputValue,
                language: 'it-IT',
                }
            })
            .then((response)=> {
                console.log(response.data.results);
                this.filmList = response.data.results;
            })
            .catch(function (error) {
                console.log(error);
            });
        }
    }
}
</script>

<style lang='scss' scoped>

</style>