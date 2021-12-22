<template>
  <header>
    <img src="" alt="logo boolflix">
    <nav>
      <input type="text" placeholder="Inserisci il titolo" v-model="inputValue">
      <button @click="$emit('search', inputValue), $emit('searchSeries', inputValue)">Cerca</button>
    </nav>
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
header{
  display: flex;
  justify-content: space-between;
}
</style>