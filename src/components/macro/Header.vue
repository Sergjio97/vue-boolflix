<template>
  <header>
    <img src="../../assets/netflix-logo-sound-1920x1080.webp" alt="logo boolflix">
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
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 80px;
  img {
    height: 50px;
  }
}
</style>