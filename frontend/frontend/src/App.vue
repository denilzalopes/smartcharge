<template>
  <div id="app">
    <h1>SmartCharge</h1>
    <ChargingStations />
  </div>
</template>

<script>
import ChargingStations from './components/ChargingStations.vue'

export default {
  name: 'App',
  components: {
    ChargingStations
  }
}
</script>