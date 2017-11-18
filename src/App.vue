<template>
  <div id="app">
    <div class="container">
      <div class="form-group">
        <input type="text" class="form-control" v-model.trim="term" />
      </div>
      <vehicle-list :vehicles="vehicles" />
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import VehicleList from './components/VehicleList'

export default {
  name: 'app',
  components: {
    VehicleList
  },
  data: () => ({
    vehicles: [],
    term: ''
  }),
  methods: {
    fetchVehicles() {
      let baseURL = `https://swapi.co/api/vehicles/?search=${this.term}`
      this.$http.get(baseURL).then(response => {
        this.vehicles = response.body.results
      }, error => {
        console.log(error)
      })
    }
  },
  mounted() {
    this.fetchVehicles()
  },
  watch: {
    term: function (val) {
      this.fetchVehicles()
    }
  }
}
</script>
