<template>
  <section>
    <div class="contents-list" v-for="(film, index) in filmList" :key="index">
      <Card :info="film"/> 
    </div>
  </section>
</template>

<script>
import Card from '../elements/Card.vue'
export default {
    name: 'SearchList',
    props: {
      filmList: Array
    },
    components: {
      Card
    }
}
</script>

<style lang='scss' scoped>
</style>