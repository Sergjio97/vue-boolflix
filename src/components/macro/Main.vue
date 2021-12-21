<template>
  <main>
      <nav>
          <Header @search="searchFilm" @searchSeries="searchSeries"/>
          <div class="films-info" v-for="(film, index) in filmList" :key="index">
            <Filmcard :info="film"/> 
          </div>
          <div class="series-info" v-for="(serie, index) in seriesList" :key="index">
            <Seriescard :info="serie"/> 
          </div>
      </nav>
  </main>
</template>

<script>
import axios from 'axios';
import Header from './Header.vue';
import Filmcard from '../elements/Filmcard.vue';
import Seriescard from '../elements/Seriescard.vue'

export default {
    name: 'Main',
    components: {
        Header,
        Filmcard,
        Seriescard
    },
    data() {
        return {
            filmList: [],
            seriesList: [],
            flags: [
                'en'
            ]
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
                this.seriesList = response.data.results;
            })
            .catch(function (error) {
                console.log(error);
            });
        },
        flagsConversion() {
            console.log('funziona')
        },
    }
}
</script>

<style lang='scss' scoped>

</style>