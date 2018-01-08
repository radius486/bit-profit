<template>
  <div class="wrapper">
    <h1>{{ msg }}</h1>
    <p class="month-profit"><span>Prifit from 1 TH/s: </span><input type="number" v-model.number='monthProfit'></p>
    <p class="month-profit"><span>1 TH/s price: </span><input type="number" v-model.number='thPrice'></p>
    <div class="bit-table">
      <div class="row-description">Month</div>
      <div class="month" v-for='(item, index) in monthes' :key='item.id'>{{index + 1}}</div>
      <div class="row-description">Power TH/s</div>
      <div class="power" v-for='item in monthes'><input type='number' v-model.number='item.power'></div>
      <div class="row-description">Reinvest TH/s</div>
      <div>-</div>
      <div class="reinvest" v-for='(item, index) in monthes' v-if='index != 0'><input type='number' v-model.number='item.reinvest'></div>
      <div class="row-description">Sum power</div>
      <div class="sum-power" v-for='(item, index) in monthes' v-html='sumPower(index)'></div>
      <div class="row-description">Profit</div>
      <div class="profit" v-for='(item, index) in monthes' v-html='month(index)'></div>
      <div class="row-description">3 month profit</div>
      <div class="three-month-profit-1" v-html='threeMonthProfit1'></div>
      <div class="three-month-profit-2" v-html='threeMonthProfit2'></div>
      <div class="three-month-profit-3" v-html='threeMonthProfit3'></div>
      <div class="three-month-profit-4" v-html='threeMonthProfit4'></div>
      <div class="row-description">Half year profit</div>
      <div class="half-profit-1" v-html='halfProfit1'></div>
      <div class="half-profit-2" v-html='halfProfit2'></div>
      <div class="row-description">Sum profit</div>
      <div class="sum-profit" v-html='sum'></div>
    </div>

    <BitCharts
      :month1='month(0)'
      :month2='month(1)'
      :month3='month(2)'
      :month4='month(3)'
      :month5='month(4)'
      :month6='month(5)'
      :month7='month(6)'
      :month8='month(7)'
      :month9='month(8)'
      :month10='month(9)'
      :month11='month(10)'
      :month12='month(11)'
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
      monthProfit: 80,
      thPrice: 150,
      monthes: [
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0},
        {power: 4, reinvest: 0}
      ],
    }
  },

  computed: {
    sum() {
      return this.month(0) + this.month(1) + this.month(2) + this.month(3) + this.month(4) + this.month(5) + this.month(6) + this.month(7) + this.month(8) + this.month(9) + this.month(10) + this.month(11);
    },

    threeMonthProfit1 () {
      return this.month(0) + this.month(1) + this.month(2);
    },

    threeMonthProfit2 () {
      return this.month(3) + this.month(4) + this.month(5);
    },

    threeMonthProfit3 () {
      return this.month(6) + this.month(7) + this.month(8);
    },

    threeMonthProfit4 () {
      return this.month(9) + this.month(10) + this.month(11);
    },

    halfProfit1() {
      return this.month(0) + this.month(1) + this.month(2) + this.month(3) + this.month(4) + this.month(5);
    },

    halfProfit2() {
      return this.month(6) + this.month(7) + this.month(8) + this.month(9) + this.month(10) + this.month(11);
    },

  },

  methods: {
    sumPower(index) {
      let sum = this.monthes[index].power;

      for(let i=0; i <= index; i++) {
        sum += this.monthes[i].reinvest;
      }

      return sum;
    },

    month(index) {
      let reinvest;

      if (index != 11) {
        reinvest = this.monthes[index + 1].reinvest * this.thPrice;
      } else {
        reinvest = 0;
      }

      return this.sumPower(index) * this.monthProfit - reinvest;
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

.month-profit
  font-size: 16px
  text-align: left

  input
    border: none
    font-size: 16px
    width: 50px
    padding-left: 5px

    &:focus
      outline: none
      background-color: #4caf50
      color: #fff


.wrapper
  max-width: 1200px
  margin: 0 auto
  padding: 0 20px


.bit-table
  display: grid
  grid-template-columns: 200px repeat(12, minmax(50px, 1fr))
  grid-template-rows: repeat(5, 30px)
  grid-gap: 2px
  border: 2px solid #000
  background-color: #000

  > div
    line-height: 30px
    background-color: #fff


.row-description
  //width: 200px

.month

.power,
.reinvest
  display: flex
  align-items: center

  input
    width: 100%
    height: 100%
    border: none
    text-align: center
    font-size: 16px
    font-weight: 300
    box-sizing: border-box
    padding: 0 0 2px 12px

    &:focus
      outline: none
      background-color: #4caf50
      color: #fff


.half-profit-1
  grid-column: 2/8


.half-profit-2
  grid-column: 8/14


.three-month-profit-1
  grid-column: 2/5


.three-month-profit-2
  grid-column: 5/8


.three-month-profit-3
  grid-column: 8/11


.three-month-profit-4
  grid-column: 11/14


.sum-profit
  grid-column: 2/14
  font-weight: 600


</style>
