<script setup>
import { ref } from 'vue'

const city = ref('Damascus')
const temperature = ref(25)
const weather = ref('Sunny')

const cities = {
  Damascus: {
    name: 'دمشق',
    temperature: 25,
    weather: '☀️ مشمس'
  },

  Hama: {
    name: 'حماة',
    temperature: 27,
    weather: '☀️ مشمس'
  },

  Homs: {
    name: 'حمص',
    temperature: 24,
    weather: '☁️ غائم'
  },

  Aleppo: {
    name: 'حلب',
    temperature: 26,
    weather: '☀️ مشمس'
  },

  Latakia: {
    name: 'اللاذقية',
    temperature: 22,
    weather: '🌧️ ممطر'
  },

  Tartus: {
    name: 'طرطوس',
    temperature: 23,
    weather: '☁️ غائم'
  },

  Idlib: {
    name: 'إدلب',
    temperature: 25,
    weather: '☀️ مشمس'
  },

  Daraa: {
    name: 'درعا',
    temperature: 28,
    weather: '☀️ مشمس'
  },

  Beirut: {
    name: 'بيروت',
    temperature: 24,
    weather: '☀️ مشمس'
  },

  Amman: {
    name: 'عمّان',
    temperature: 23,
    weather: '☁️ غائم'
  },

  Cairo: {
    name: 'القاهرة',
    temperature: 30,
    weather: '☀️ مشمس'
  },

  Baghdad: {
    name: 'بغداد',
    temperature: 35,
    weather: '☀️ مشمس'
  },

  Riyadh: {
    name: 'الرياض',
    temperature: 38,
    weather: '☀️ مشمس'
  },

  Dubai: {
    name: 'دبي',
    temperature: 36,
    weather: '☀️ مشمس'
  },

  Doha: {
    name: 'الدوحة',
    temperature: 37,
    weather: '☀️ مشمس'
  },

  Tunis: {
    name: 'تونس',
    temperature: 26,
    weather: '☁️ غائم'
  },

  Algiers: {
    name: 'الجزائر',
    temperature: 25,
    weather: '☀️ مشمس'
  },

  Rabat: {
    name: 'الرباط',
    temperature: 22,
    weather: '☁️ غائم'
  },

  'Deir-Ezzor': {
    name: 'دير الزور',
    temperature: 40,
    weather: '☀️ مشمس'
  }
}

function selectCity() {
  const selectedCity = cities[city.value]

  temperature.value = selectedCity.temperature
  weather.value = selectedCity.weather
}
</script>

<template>
  <div class="dashboard">

    <h1>🌤️ Weather Dashboard</h1>

    <div class="search">

      <select v-model="city" @change="selectCity">

        <option
          v-for="(data, key) in cities"
          :key="key"
          :value="key"
        >
          {{ data.name }}
        </option>

      </select>

    </div>

    <div class="weather-card">

      <h2>{{ cities[city].name }}</h2>

      <div class="temperature">
        {{ temperature }}°C
      </div>

      <p class="condition">
        {{ weather }}
      </p>

      <div class="details">

        <div>
          <span>💧</span>
          <p>Humidity</p>
          <strong>70%</strong>
        </div>

        <div>
          <span>💨</span>
          <p>Wind</p>
          <strong>12 km/h</strong>
        </div>

      </div>

    </div>

  </div>
</template>