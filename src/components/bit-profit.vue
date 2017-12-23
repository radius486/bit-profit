<template>
  <div class="wrapper">
    <h1>{{ msg }}</h1>
    <div class="bit-table">
      <div class="row-description">Month</div>
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
      <div class="row-description">Power</div>
      <div class="power"><input type='number' v-model.number='power1'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power2'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power3'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power4'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power5'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power6'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power7'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power8'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power9'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power10'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power11'>TH/s</div>
      <div class="power"><input type='number' v-model.number='power12'>TH/s</div>
      <div class="row-description">Reinvest</div>
      <div>-</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest2'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest3'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest4'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest5'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest6'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest7'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest8'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest9'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest10'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest11'>TH/s</div>
      <div class="reinvest"><input type='number' v-model.number='reinvest12'>TH/s</div>
      <div class="row-description">Sum power</div>
      <div class="sum-power" v-html='sumPower1'></div>
      <div class="sum-power" v-html='sumPower2'></div>
      <div class="sum-power" v-html='sumPower3'></div>
      <div class="sum-power" v-html='sumPower4'></div>
      <div class="sum-power" v-html='sumPower5'></div>
      <div class="sum-power" v-html='sumPower6'></div>
      <div class="sum-power" v-html='sumPower7'></div>
      <div class="sum-power" v-html='sumPower8'></div>
      <div class="sum-power" v-html='sumPower9'></div>
      <div class="sum-power" v-html='sumPower10'></div>
      <div class="sum-power" v-html='sumPower11'></div>
      <div class="sum-power" v-html='sumPower12'></div>
      <div class="row-description">Profit</div>
      <div class="profit" v-html='month1'></div>
      <div class="profit" v-html='month2'></div>
      <div class="profit" v-html='month3'></div>
      <div class="profit" v-html='month4'></div>
      <div class="profit" v-html='month5'></div>
      <div class="profit" v-html='month6'></div>
      <div class="profit" v-html='month7'></div>
      <div class="profit" v-html='month8'></div>
      <div class="profit" v-html='month9'></div>
      <div class="profit" v-html='month10'></div>
      <div class="profit" v-html='month11'></div>
      <div class="profit" v-html='month12'></div>
      <div class="row-description">Sum profit</div>
      <div class="sum-profit">{{sum}}</div>
    </div>

    <BitCharts
      :month1='month1'
      :month2='month2'
      :month3='month3'
      :month4='month4'
      :month5='month5'
      :month6='month6'
      :month7='month7'
      :month8='month8'
      :month9='month9'
      :month10='month10'
      :month11='month11'
      :month12='month12'
      ></BitCharts>
  </div>
</template>

<script>
import BitCharts from './bit-charts'

export default {
  name: 'BitProfit',

  components: {
    BitCharts
  },

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
      power12: 4,
      reinvest1: 0,
      reinvest2: 0,
      reinvest3: 0,
      reinvest4: 0,
      reinvest5: 0,
      reinvest6: 0,
      reinvest7: 0,
      reinvest8: 0,
      reinvest9: 0,
      reinvest10: 0,
      reinvest11: 0,
      reinvest12: 0
    }
  },

  computed: {
    sum() {
      return this.month1 + this.month2 + this.month3 + this.month4 + this.month5 + this.month6 + this.month7 + this.month8 + this.month9 + this.month10 + this.month11 + this.month12;
    },

    sumPower1() {
      return this.power1 + this.reinvest1;
    },

    sumPower2() {
      return this.power2 + this.reinvest1 + this.reinvest2;
    },

    sumPower3() {
      return this.power3 + this.reinvest1 + this.reinvest2 + this.reinvest3;
    },

    sumPower4() {
      return this.power4 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4;
    },

    sumPower5() {
      return this.power5 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5;
    },

    sumPower6() {
      return this.power6 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6;
    },

    sumPower7() {
      return this.power7 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7;
    },

    sumPower8() {
      return this.power8 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7 + this.reinvest8;
    },

    sumPower9() {
      return this.power9 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7 + this.reinvest8 + this.reinvest9;
    },

    sumPower10() {
      return this.power10 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7 + this.reinvest8 + this.reinvest9 + this.reinvest10;
    },

    sumPower11() {
      return this.power11 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7 + this.reinvest8 + this.reinvest9 + this.reinvest10 + this.reinvest11;
    },

    sumPower12() {
      return this.power12 + this.reinvest1 + this.reinvest2 + this.reinvest3 + this.reinvest4 + this.reinvest5 + this.reinvest6 + this.reinvest7 + this.reinvest8 + this.reinvest9 + this.reinvest10 + this.reinvest11 + this.reinvest12;
    },

    month1 () {
      return this.sumPower1 * 80 - this.reinvest2 * 150;
    },

    month2 () {
      return this.sumPower2 * 80 - this.reinvest3 * 150;
    },

    month3 () {
      return this.sumPower3 * 80 - this.reinvest4 * 150;
    },

    month4 () {
      return this.sumPower4 * 80 - this.reinvest5 * 150;
    },

    month5 () {
      return this.sumPower5 * 80 - this.reinvest6 * 150;
    },

    month6 () {
      return this.sumPower6 * 80 - this.reinvest7 * 150;
    },

    month7 () {
      return this.sumPower7 * 80 - this.reinvest8 * 150;
    },

    month8 () {
      return this.sumPower8 * 80 - this.reinvest9 * 150;
    },

    month9 () {
      return this.sumPower9 * 80 - this.reinvest10 * 150;
    },

    month10 () {
      return this.sumPower10 * 80 - this.reinvest11 * 150;
    },

    month11 () {
      return this.sumPower11 * 80 - this.reinvest12 * 150;
    },

    month12 () {
      return this.sumPower12 * 80;
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
  grid-template-columns: repeat(13, minmax(50px, 1fr))
  grid-template-rows: repeat(5, 30px)
  grid-gap: 2px
  border: 2px solid #000
  background-color: #000

  > div
    line-height: 30px
    background-color: #fff

.month

.power,
.reinvest
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
  grid-column: 2/14
  font-weight: 600


</style>
