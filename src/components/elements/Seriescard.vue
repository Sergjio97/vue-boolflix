<template>
  <section>
    <h3>Titolo: {{info.name}}</h3>
    <h4>Titolo Originale: {{info.original_name}}</h4>
    <h5>Lingua: {{info.original_language}}</h5>
    <h5>Valutazione: {{info.vote_average}}</h5>
  </section>
</template>

<script>
export default {
    name: 'Seriescard',
    props: {
        info: Object
    }
}
</script>

<style>

</style>