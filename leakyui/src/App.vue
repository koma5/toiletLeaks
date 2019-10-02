<template>
  <div id="app">
    <Add />
    <Search />
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Add from './components/Add.vue'

export default {
    name: 'app',
    components: {
    Search,
    Add
    },
    created() {
        this.$pouch.connect('user', 'user', 'https://database.shameless-postcard-queue.5th.ch/test')
        this.$pouch.sync('https://database.shameless-postcard-queue.5th.ch/test')

    }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
