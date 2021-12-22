<template>
  <div class="card-box"  style="background-image: url('../../assets/flags/pirate.png')">
    <h3>Titolo: {{info.title ? info.title : info.name}}</h3>
    <h4>Titolo Originale: {{info.original_title ? info.original_title : info.original_name}}</h4>
    <img v-if="flagsList.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language" height="30">
    <img v-else src="../../assets/flags/pirate.png" height="30" alt="bandiera non disponibile">
    <h4>Valutazione: {{Math.ceil(info.vote_average / 2)}}</h4>
    <img id="poster" :src="'https://image.tmdb.org/t/p/w342' + info.poster_path"  :alt="'Poster: '+info.title">
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
  }
}
</script>

<style lang='scss' scoped>
.card-box {
  width: 100%;
  color: #fff;
  #poster {
    width: 100%;
  }
}
</style>