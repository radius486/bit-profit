<template>
  <div id="app">
    <BitProfit/>
  </div>
</template>

<script>
import BitProfit from './components/bit-profit'

export default {
  name: 'app',
  components: {
    BitProfit
  }
}
</script>

<style lang="sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 60px

</style>
