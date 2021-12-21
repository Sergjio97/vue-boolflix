<template>
  <header>
    <input type="text" placeholder="inserisci il titolo" v-model="inputValue">
    <button @click="$emit('search', inputValue), $emit('searchSeries', inputValue)">Cerca</button>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
      return {
        inputValue: '',
      }
    }
}
</script>

<style lang="scss" scoped>

</style>