<template>
  <div class="wrapper">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'BitProfit',
  data () {
    return {
      msg: 'Calculate profit.'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
h1,
h2
  font-weight: normal
  color: #f0f

.wrapper
  max-width: 1200px
  margin: 0 auto
  padding: 0 20px

</style>
