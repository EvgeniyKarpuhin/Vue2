<script setup>

import { computed, ref } from 'vue'

const weather = ref({
  data() {
    return {
      city: "",
      error: "",
      info: null
    }
  },
  computed: {
    cityName() {
      return "«" + this.city + "»"
    }
  },
  methods: {
    getWeather() {
      if(this.city.trim().lengt <2) {
        this.error = "Нужно название более 2 символов"
        return false
      }
      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=a059085e330fce68f911321b65962676`)
      .then(res => (this.info = res.data))
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
    <p class="error">{{ error }}</p>

  </div>
</template>


