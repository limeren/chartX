<template>
  <canvas id="chart"
          ref="renderChart"
          :width="sizeX"
          :height="sizeY">Canvas is not supported!
  </canvas>
</template>

<script>
export default {
  name: 'ChartCanvas',
  data() {
    return {
      canvas: 'canvas',
      scaleY: 50,
      maxY: 300,
      scaleX: 1,
      maxX: 14,
      sizeX: 900,
      sizeY: 500,
      test1: [100, 223, 110, 350, 57, 67, 237, 29],
      chartNumDistance: 5,
    };
  },
  methods: {
    updateCanvas() {
      const canvas = this.$refs.renderChart;
      const ctx = canvas.getContext('2d');
      ctx.beginPath();
      ctx.strokeStyle = '#d8d8d8';
      ctx.font = '14px Verdana';
      ctx.fillStyle = '#d8d8d8';
      for (let i = 0; i <= this.sizeY; i += this.scaleY) {
        const flipCoordinates = this.sizeY - i;
        ctx.moveTo(0, flipCoordinates);
        ctx.lineTo(this.sizeX, flipCoordinates);
        ctx.fillText(i.toString(), this.chartNumDistance, flipCoordinates - this.chartNumDistance);
        ctx.stroke();
        console.log(i);
      }
    },
    dataRender() {
      const canvas = this.$refs.renderChart;
      const ctx = canvas.getContext('2d');
      ctx.beginPath();
      ctx.strokeStyle = '#00ff00';
      for (let i = 0; i < this.test1.length; i += 1) {
        ctx.lineTo(i * 50, this.test1[i]);
        ctx.stroke();
        console.log(i);
      }
    },
  },
  mounted() {
    this.updateCanvas();
    this.dataRender();
  },
};
</script>

<style scoped>

</style>
