<template>
  <h1>{{ msg }}</h1>
  <br />
  <br />

  <template v-for="(interval, index) in intervals" :key="index">
    <IntervalComponent @remove="removeInterval(index)" v-model:duration="interval.duration"  />
  </template>

  <div class="row">
    <div class="col">
      <button @click="addInterval()" class="btn btn-primary">Legg til</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import IntervalComponent from './Interval.vue'

export default {
  name: 'PlannerComponent',
  props: {
    msg: String
  },
  components: {
    IntervalComponent
  },
  setup() {
    const intervals = ref([ {duration:20}]);
    function addInterval() {
      intervals.value.push({duration:20});
    }
    function removeInterval(index) {
      intervals.value.splice(index,1);
    }
    return {
      intervals,
      addInterval,
      removeInterval
    };
  }  
}
</script>