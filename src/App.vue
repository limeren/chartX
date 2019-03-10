<template>
  <div id="app">
    <ChartCanvas/>
  </div>
</template>

<script>
import ChartCanvas from './components/ChartCanvas';

export default {
  name: 'App',
  components: {
    ChartCanvas,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
