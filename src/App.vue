<template>
  <photo-charts></photo-charts>
  <second-photo></second-photo>
</template>

<script>
import PhotoCharts from "@/components/photo-charts.vue";
import SecondPhoto from "@/components/second-photo.vue";

export default {
  name: 'App',
  components: {
    SecondPhoto,
    PhotoCharts,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
