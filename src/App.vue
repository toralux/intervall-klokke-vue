<template>
  <div class="container-fluid">
    <PlannerComponent msg="Treningsplanlegger"/>
  </div>
</template>

<script>
import PlannerComponent from './components/Planner.vue'

export default {
  name: 'App',
  components: {
    PlannerComponent
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
