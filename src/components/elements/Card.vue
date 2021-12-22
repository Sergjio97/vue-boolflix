<template>
  <div>
    <h3>Titolo: {{info.title ? info.title : info.name}}</h3>
    <h4>Titolo Originale: {{info.original_title ? info.original_title : info.original_name}}</h4>
    <img v-if="flagsList.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language" height="30">
    <img v-else src="../../assets/flags/pirate.png" height="30" alt="bandiera non disponibile">
    <h4>Valutazione: {{info.vote_average}}</h4>
    <img :src="'https://image.tmdb.org/t/p/w342' + info.poster_path"  :alt="'Poster: '+info.title">
  </div>
</template>

<script>
export default {
  name: 'Card',
  data() {
    return {
      flagsList: [
        'en',
        'it',
        'fr',
        'ja'
      ]
    }
  },
  props: {
    info: Object
  },
}
</script>

<style lang='scss' scoped>
</style>