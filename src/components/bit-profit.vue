<template>
  <div class="wrapper">
    <h1>{{ msg }}</h1>
    <div class="bit-table">
      <div class="month">1</div>
      <div class="month">2</div>
      <div class="month">3</div>
      <div class="month">4</div>
      <div class="month">5</div>
      <div class="month">6</div>
      <div class="month">7</div>
      <div class="month">8</div>
      <div class="month">9</div>
      <div class="month">10</div>
      <div class="month">11</div>
      <div class="month">12</div>
      <div class="power"><input type='text' v-model='power1'>TH/s</div>
      <div class="power"><input type='text' v-model='power2'>TH/s</div>
      <div class="power"><input type='text' v-model='power3'>TH/s</div>
      <div class="power"><input type='text' v-model='power4'>TH/s</div>
      <div class="power"><input type='text' v-model='power5'>TH/s</div>
      <div class="power"><input type='text' v-model='power6'>TH/s</div>
      <div class="power"><input type='text' v-model='power7'>TH/s</div>
      <div class="power"><input type='text' v-model='power8'>TH/s</div>
      <div class="power"><input type='text' v-model='power9'>TH/s</div>
      <div class="power"><input type='text' v-model='power10'>TH/s</div>
      <div class="power"><input type='text' v-model='power11'>TH/s</div>
      <div class="power"><input type='text' v-model='power12'>TH/s</div>
      <div class="profit" v-html='month1'></div>
      <div class="profit">{{power2 * 80}}</div>
      <div class="profit">{{power3 * 80}}</div>
      <div class="profit">{{power4 * 80}}</div>
      <div class="profit">{{power5 * 80}}</div>
      <div class="profit">{{power6 * 80}}</div>
      <div class="profit">{{power7 * 80}}</div>
      <div class="profit">{{power8 * 80}}</div>
      <div class="profit">{{power9 * 80}}</div>
      <div class="profit">{{power10 * 80}}</div>
      <div class="profit">{{power11 * 80}}</div>
      <div class="profit">{{power12 * 80}}</div>
      <div class="sum-profit">{{sum}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BitProfit',
  data () {
    return {
      msg: 'Calculate profit.',
      power1: 4,
      power2: 4,
      power3: 4,
      power4: 4,
      power5: 4,
      power6: 4,
      power7: 4,
      power8: 4,
      power9: 4,
      power10: 4,
      power11: 4,
      power12: 4
    }
  },

  computed: {
    sum() {
      return this.month1 + this.month2 + this.month3 + this.month4 + this.month5 + this.month6 + this.month7 + this.month8 + this.month9 + this.month10 + this.month11 + this.month12;
    },

    month1 () {
      return this.power1 * 80;
    },

    month2 () {
      return this.power2 * 80;
    },

    month3 () {
      return this.power3 * 80;
    },

    month4 () {
      return this.power4 * 80;
    },

    month5 () {
      return this.power5 * 80;
    },

    month6 () {
      return this.power6 * 80;
    },

    month7 () {
      return this.power7 * 80;
    },

    month8 () {
      return this.power8 * 80;
    },

    month9 () {
      return this.power9 * 80;
    },

    month10 () {
      return this.power10 * 80;
    },

    month11 () {
      return this.power11 * 80;
    },

    month12 () {
      return this.power12 * 80;
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


.bit-table
  display: grid
  grid-template-columns: repeat(12, minmax(50px, 1fr))
  grid-template-rows: repeat(3, 24px)
  grid-gap: 2px
  border: 2px solid #000
  background-color: #000

  > div
    line-height: 24px
    background-color: #fff

.month

.power
  display: flex
  align-items: center

  input
    width: 50%
    height: 100%
    border: none
    text-align: right
    font-size: 16px
    font-weight: 300
    box-sizing: border-box
    padding: 0 0 2px

    &:hover,
    &:focus
      outline: none


.sum-profit
  grid-column: 1/13
  font-weight: 600


</style>
