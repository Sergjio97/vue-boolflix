<template>
  <section>
    <h3>Titolo: {{info.name}}</h3>
    <h4>Titolo Originale: {{info.original_name}}</h4>
    <h4>Lingua: {{info.original_language}}</h4>
    <h4>Valutazione: {{info.vote_average}}</h4>
  </section>
</template>

<script>
export default {
    name: 'Seriescard',
    props: {
        info: Object
    },
    methods: {
    }
}
</script>

<style>

</style>