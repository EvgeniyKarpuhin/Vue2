<script setup>
import { ref } from 'vue'

const weather = ref({
  data() {
    return {
      city: ""
    }
  }
})
</script>

<template>
  <div class="wrapper">
    <h1>Погодное приложение</h1>
    <P>Узнать погоду в {{ city == "" ? "вашем городе" : city }}</P>
    <input type="text" v-model="city" placeholder="Введите город">
    <button>Получить погоду</button>
  </div>
</template>


