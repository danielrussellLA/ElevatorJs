<template>
  <div id="app">
    <Elevator :floors="floors"/>
  </div>
</template>

<script>
import Elevator from './components/Elevator.vue'

export default {
  name: 'app',
  components: {
    Elevator
  },
  data() {
      return {
          floors: [
              {level: 2, isPressed: false},
              {level: 1, isPressed: false},
              {level: 0, isPressed: false},
          ]
      }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
