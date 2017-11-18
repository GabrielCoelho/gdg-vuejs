<template>
  <ul class="list-group">
    <vehicle-item v-for="vehicle in vehicles" :key="vehicle.model" v-bind:item="vehicle" />
  </ul>
</template>
<script>
import VehicleItem from './VehicleItem'

  export default {
    props: {
      vehicles: {
        type: Array,
        required: true
      }
    },
    components: {
      VehicleItem
    }
  }
</script>