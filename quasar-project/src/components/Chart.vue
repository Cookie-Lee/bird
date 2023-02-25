<template>
  <div :id="id" style="width: 100%; height: 400px"></div>
</template>

<script>
export default {
  props: ["id", "option"],

  mounted() {
    this.echarts();
  },

  methods: {
    echarts() {
      var echarts = require("echarts");
      var myChart = echarts.init(document.getElementById(this.id));
      window.addEventListener("resize", function () {
        myChart.resize();
      });
      myChart.setOption(this.option);
    },
  },
};
</script>
