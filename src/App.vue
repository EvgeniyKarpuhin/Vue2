<script>
export default {
  data() {
    return {
      city: ""
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <h1>Погодное приложение</h1>
    <P>Узнать погоду в {{ city }}</P>
    <input type="text" @input="this.city = $event.target.value" placeholder="Введите город">
    <button>Получить погоду</button>
  </div>
</template>


