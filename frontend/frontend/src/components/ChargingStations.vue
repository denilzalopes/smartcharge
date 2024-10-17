<template>
  <div>
    <h2>Charging Stations</h2>
    <ul v-if="stations.length">
      <li v-for="station in stations" :key="station.id">
        {{ station.name }} - {{ station.location }} ({{ station.status }})
      </li>
    </ul>
    <p v-else>No charging stations found.</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      stations: []
    }
  },
  mounted() {
    this.fetchStations()
  },
  methods: {
    async fetchStations() {
      try {
        const response = await axios.get('/api/charging-stations')
        this.stations = response.data
      } catch (error) {
        console.error('Error fetching stations:', error)
      }
    }
  }
}
</script>