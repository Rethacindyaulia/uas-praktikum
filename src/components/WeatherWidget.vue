<template>
  <div class="weather-widget">
    <h2>Weather Widget</h2>
    <div class="search-bar">
      <input v-model="city" placeholder="Enter city name" @keyup.enter="getWeather" />
      <button @click="getWeather">Search</button>
    </div>
    <div v-if="weather" class="weather-info">
      <p><strong>Location:</strong> {{ weather.name }}</p>
      <p><strong>Temperature:</strong> {{ weather.main.temp }}°C</p>
      <p><strong>Weather:</strong> {{ weather.weather[0].description }}</p>
    </div>
    <div v-else>
      <p>Enter a city name to see the weather.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const city = ref('')
const weather = ref(null)

const getWeather = async () => {
  const apiKey = '23f0987b01236b80c30ceeb06f7c8c22'
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`

  try {
    const response = await axios.get(url)
    weather.value = response.data
  } catch (error) {
    console.error(error)
    weather.value = null
  }
}
</script>

<style scoped>
.weather-widget {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  max-width: 600px;
  margin: 20px auto;
  text-align: center;
  background-color: #f0e4f7;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.weather-widget h2 {
  color: #5a3d6f;
  font-size: 36px;
  font-weight: bold;
  margin-bottom: -1px;
}

.search-bar {
  margin-bottom: 20px;
}

.search-bar input {
  padding: 10px;
  width: calc(100% - 22px);
  margin-right: 2px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fffafc;
}

.search-bar button {
  padding: 10px;
  border: 1px solid whitesmoke;
  background-color: #7b4b94;
  color: white;
  cursor: pointer;
  border-radius: 5px;
  margin-top: 10px;
}

.search-bar button:hover {
  background-color: #5a3d6f;
}

.weather-info {
  margin-top: 20px;
}

.weather-info p {
  margin: 5px 0;
  color: #5a3d6f;
}
</style>
