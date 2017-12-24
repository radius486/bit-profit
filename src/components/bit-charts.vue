<template>
  <div class="wrapper">
    <h1 @click.prevent='drawChart'>{{ msg }}</h1>
    <canvas id="chart" width="602" height="300">{{sum}}</canvas>
  </div>
</template>

<script>
//import Highcharts from 'highcharts'

export default {
  name: 'BitCharts',

  props: [
    'month1',
    'month2',
    'month3',
    'month4',
    'month5',
    'month6',
    'month7',
    'month8',
    'month9',
    'month10',
    'month11',
    'month12'
  ],

  data() {
    return {
      msg: 'Charts',
      ctx: undefined,
      gCanvasElement: undefined
    }
  },

  mounted() {
    this.gCanvasElement = document.getElementById("chart");
    this.ctx = this.gCanvasElement.getContext("2d");
    this.drawChart();

  },

  computed: {
    sum() {
      if (this.ctx) {
        this.clearCanvas();
        this.drawChart();
        return this.$parent.sum;
      }
    }

  },

  methods: {
    drawChart() {
      let ctx = this.ctx;
      let h = this.gCanvasElement.height;
      ctx.fillStyle = '#673ab7';
      ctx.fillRect(2, h - this.month1/10, 48, this.month1/10);
      ctx.fillRect(52, h - this.month2/10, 48, this.month2/10);
      ctx.fillRect(102, h - this.month3/10, 48, this.month3/10);
      ctx.fillRect(152, h - this.month4/10, 48, this.month4/10);
      ctx.fillRect(202, h - this.month5/10, 48, this.month5/10);
      ctx.fillRect(252, h - this.month6/10, 48, this.month6/10);
      ctx.fillRect(302, h - this.month7/10, 48, this.month7/10);
      ctx.fillRect(352, h - this.month8/10, 48, this.month8/10);
      ctx.fillRect(402, h - this.month9/10, 48, this.month9/10);
      ctx.fillRect(452, h - this.month10/10, 48, this.month10/10);
      ctx.fillRect(502, h - this.month11/10, 48, this.month11/10);
      ctx.fillRect(552, h - this.month12/10, 48, this.month12/10);
      ctx.fillStyle = "#ff9800";
      ctx.font = "20pt Arial";
      ctx.fillText(this.$parent.sum, 10, 30);
      ctx.fillStyle = "#4caf50";
      ctx.font = "14pt Arial";
      ctx.textAlign = "center";
      ctx.fillText(this.month1, 26, h - this.month1/10 - 2);
      ctx.fillText(this.month2, 76, h - this.month2/10 - 2);
      ctx.fillText(this.month3, 126, h - this.month3/10 - 2);
      ctx.fillText(this.month4, 176, h - this.month4/10 - 2);
      ctx.fillText(this.month5, 226, h - this.month5/10 - 2);
      ctx.fillText(this.month6, 276, h - this.month6/10 - 2);
      ctx.fillText(this.month7, 326, h - this.month7/10 - 2);
      ctx.fillText(this.month8, 376, h - this.month8/10 - 2);
      ctx.fillText(this.month9, 426, h - this.month9/10 - 2);
      ctx.fillText(this.month10, 476, h - this.month10/10 - 2);
      ctx.fillText(this.month11, 526, h - this.month11/10 - 2);
      ctx.fillText(this.month12, 576, h - this.month12/10 - 2);
    },

    clearCanvas() {
      this.gCanvasElement.width = this.gCanvasElement.width;
    }
  }
}
</script>

<style lang="sass" scoped>
  .wrapper
    max-width: 1200px
    margin: 0 auto
    padding: 0 20px

  #chart
    border: 1px solid #000

</style>
