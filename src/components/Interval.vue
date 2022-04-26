cons<template>
  <div class="row m-5">
    <div class="col">
      <button @click="this.$emit('remove')" class="btn btn-primary">Slett</button>
    </div>
    <div class="col">
      <vue3-slider :modelValue="duration" @change="$emit('update:duration', $event)" :height="15"
        :min="10" :max="90" v-bind:step="10" 
        color="#000000" track-color="#FFFFFF" 
        :tooltip="true" :alwaysShowTooltip="true" tooltipText="%v minutter" tooltipColor="#FFFFFF" tooltipTextColor="#000000"
      />
    </div>
    <div class="col">{{duration}}</div>    
  </div>
</template>

<style>
  .tooltip {
    opacity: 1;
  }
</style>

<script>
import slider from "vue3-slider"

export default {
  name: 'IntervalComponent',
  components: {
    'vue3-slider': slider,
  },
  props: {
    duration: {
      type: Number,
      default: 10
    }
  },
  emits: ['update:duration'],
}
</script>