<script setup>
import { computed, ref } from 'vue'

const weather = ref({
  data() {
    return {
      city: ""
    }
  },
  computed: {
    cityName() {
      return "«" + this.city + "»"
    }
  },
  methods: {
    getWeather() {
      alert("Some")
    }
  }
})
</script>

<template>
  <div class="wrapper">
    <h1>Погодное приложение</h1>
    <p>Узнать погоду в {{ weather.city == "" ? "вашем городе" : computed.cityName }}</p>
    <input type="text" v-model="weather.city" placeholder="Введите город">
    <button v-if="weather.city != ''" @click="getWeather()">Получить погоду</button>
    <button disabled v-else>Введите название города</button>
  </div>
</template>


