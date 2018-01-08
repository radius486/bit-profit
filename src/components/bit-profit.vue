<template>
  <div class="wrapper">
    <h1>{{ msg }}</h1>
    <p class="month-profit"><span>Prifit from 1 TH/s: </span><input type="number" v-model.number='monthProfit'></p>
    <p class="month-profit"><span>1 TH/s price: </span><input type="number" v-model.number='thPrice'></p>
    <div class="bit-table">
      <div class="row-description">Month</div>
      <div class="month" v-for='(item, index) in powers' :key='item.id'>{{index + 1}}</div>
      <div class="row-description">Power TH/s</div>
      <div class="power" v-for='item in powers'><input type='number' v-model.number='item.power'></div>
      <div class="row-description">Reinvest TH/s</div>
      <div>-</div>
      <div class="reinvest" v-for='(item, index) in powers' v-if='index != 0'><input type='number' v-model.number='item.reinvest'></div>
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
      monthProfit: 80,
      thPrice: 150,
      powers: [
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
      return this.month1 + this.month2 + this.month3 + this.month4 + this.month5 + this.month6 + this.month7 + this.month8 + this.month9 + this.month10 + this.month11 + this.month12;
    },

    threeMonthProfit1 () {
      return this.month1 + this.month2 + this.month3;
    },

    threeMonthProfit2 () {
      return this.month4 + this.month5 + this.month6;
    },

    threeMonthProfit3 () {
      return this.month7 + this.month8 + this.month9;
    },

    threeMonthProfit4 () {
      return this.month10 + this.month11 + this.month12;
    },

    halfProfit1() {
      return this.month1 + this.month2 + this.month3 + this.month4 + this.month5 + this.month6;
    },

    halfProfit2() {
      return this.month7 + this.month8 + this.month9 + this.month10 + this.month11 + this.month12;
    },

    sumPower1() {
      return this.powers[0].power + this.powers[0].reinvest;
    },

    sumPower2() {
      return this.powers[1].power + this.powers[0].reinvest + this.powers[1].reinvest;
    },

    sumPower3() {
      return this.powers[2].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest;
    },

    sumPower4() {
      return this.powers[3].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest;
    },

    sumPower5() {
      return this.powers[4].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest;
    },

    sumPower6() {
      return this.powers[5].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest;
    },

    sumPower7() {
      return this.powers[6].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest;
    },

    sumPower8() {
      return this.powers[7].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest + this.powers[7].reinvest;
    },

    sumPower9() {
      return this.powers[8].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest + this.powers[7].reinvest + this.powers[8].reinvest;
    },

    sumPower10() {
      return this.powers[9].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest + this.powers[7].reinvest + this.powers[8].reinvest + this.powers[9].reinvest;
    },

    sumPower11() {
      return this.powers[10].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest + this.powers[7].reinvest + this.powers[8].reinvest + this.powers[9].reinvest + this.powers[10].reinvest;
    },

    sumPower12() {
      return this.powers[11].power + this.powers[0].reinvest + this.powers[1].reinvest + this.powers[2].reinvest + this.powers[3].reinvest + this.powers[4].reinvest + this.powers[5].reinvest + this.powers[6].reinvest + this.powers[7].reinvest + this.powers[8].reinvest + this.powers[9].reinvest + this.powers[10].reinvest + this.powers[11].reinvest;
    },

    month1 () {
      return this.sumPower1 * this.monthProfit - this.powers[1].reinvest * this.thPrice;
    },

    month2 () {
      return this.sumPower2 * this.monthProfit - this.powers[2].reinvest * this.thPrice;
    },

    month3 () {
      return this.sumPower3 * this.monthProfit - this.powers[3].reinvest * this.thPrice;
    },

    month4 () {
      return this.sumPower4 * this.monthProfit - this.powers[4].reinvest * this.thPrice;
    },

    month5 () {
      return this.sumPower5 * this.monthProfit - this.powers[5].reinvest * this.thPrice;
    },

    month6 () {
      return this.sumPower6 * this.monthProfit - this.powers[6].reinvest * this.thPrice;
    },

    month7 () {
      return this.sumPower7 * this.monthProfit - this.powers[7].reinvest * this.thPrice;
    },

    month8 () {
      return this.sumPower8 * this.monthProfit - this.powers[8].reinvest * this.thPrice;
    },

    month9 () {
      return this.sumPower9 * this.monthProfit - this.powers[9].reinvest * this.thPrice;
    },

    month10 () {
      return this.sumPower10 * this.monthProfit - this.powers[10].reinvest * this.thPrice;
    },

    month11 () {
      return this.sumPower11 * this.monthProfit - this.powers[11].reinvest * this.thPrice;
    },

    month12 () {
      return this.sumPower12 * this.monthProfit;
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
