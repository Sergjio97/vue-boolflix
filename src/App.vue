<template>
  <div id="app">
    <Header @search="searchFilm" @searchSeries="searchSeries"/>
    <Main :filmList="filmList"/>
    <Footer/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/macro/Header.vue';
import Main from './components/macro/Main.vue';
import Footer from './components/macro/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data() {
    return {
      filmList: [],
    }
  },
  methods: {
    // funzione per la ricerca dei film
    searchFilm(payload) {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'eebcf7c938b9bfe34e05762eae2bec88',
          query: payload,
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
    },
    // funzione per la ricerca delle serie tv
    searchSeries(payload) {
      axios.get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: 'eebcf7c938b9bfe34e05762eae2bec88',
          query: payload,
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
    },
  }
}
</script>

<style lang="scss">
</style>
