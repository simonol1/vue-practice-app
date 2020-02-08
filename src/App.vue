<template>
  <div id="app">
    <RaceFilter></RaceFilter>
    <RaceList></RaceList>
  </div>
</template>

<script>
import RaceFilter from './components/RaceFilter.vue'
import RaceList from './components/RaceList.vue'

export default {
  name: 'App',
  components: {
    RaceFilter,
    RaceList
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
