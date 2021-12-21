<template>
  <section>
    <h3>Titolo: {{info.title}}</h3>
    <h4>Titolo Originale: {{info.original_title}}</h4>
    <h4>Lingua: {{info.original_language}}</h4>
    <h4>Valutazione: {{info.vote_average}}</h4>
    <img :src="'https://image.tmdb.org/t/p/w342' + info.poster_path"  :alt="'Poster: '+info.title">
  </section>
</template>

<script>
export default {
    name: 'Filmcard',
    data() {
      return {
        flags: [
          'en'
        ]
      }
    } ,
    props: {
        info: Object
    },
    methods: {
    }
}
</script>

<style>

</style>