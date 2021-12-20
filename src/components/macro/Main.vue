<template>
  <main>
      <nav>
          <input type="text" placeholder="inserisci il titolo" v-model="inputValue">
          <button @click="searchFilm">Cerca</button>
      </nav>
  </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data() {
        return {
            inputValue: '',
        }
    },
    methods: {
        searchFilm() {
            axios.get('/user', {
                params: {
                api_key: 'eebcf7c938b9bfe34e05762eae2bec88',
                query: this.inputValue
                }
            })
            .then(function (response) {
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            });
        }
    }
}
</script>

<style lang='scss' scoped>

</style>