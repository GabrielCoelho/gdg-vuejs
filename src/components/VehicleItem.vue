<template>
  <li class="list-group-item">
    {{ nameWithManufacturer }}
    - {{ item.passengers | passengersCount }}
  </li>
</template>
<script>
  export default {
    props: ['item'],
    computed: {
      nameWithManufacturer() {
        return`${this.item.model} (${this.item.manufacturer})`
      }
    },
    filters: {
      passengersCount(value) {
        if (value === 1) {
          return `${value} passengers`
        } else {
          return `${value} passenger`
        }
      }
    }
  }
</script>