<template>
  <main>
      <nav>
          <SearchList :filmList="filmList"/>
      </nav>
  </main>
</template>

<script>
import SearchList from '../section/SearchList.vue';

export default {
    name: 'Main',
    components: {
        SearchList
    },
    props: {
        filmList: Array
    }
}
</script>

<style lang='scss' scoped>

</style>