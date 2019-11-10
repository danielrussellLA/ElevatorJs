<template>
  <div class="elevator">
      <h1>Elevator JS</h1>
      <div v-for="floor, index in floors" class="floor" :id="`floor-${floor.level}`" @click="onFloorPressed">
          <div v-if="index === floors.length - 1" class="elevator-car" id="elevator-car">
              elevator car
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Elevator',
  props: {
      floors: Array
  },
  data() {
      return {
          elevatorCar: null
      }
  },
  mounted() {
      this.elevatorCar = document.getElementById('elevator-car');
  },
  methods: {
      onFloorPressed(e) {
          const {offsetTop} = e.srcElement;
          this.elevatorCar.style.top = offsetTop + 'px';
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.floor {
    height: 200px;
    width: 200px;
    margin: auto;
    border: 1px solid black;
}
.floor:hover {
    cursor: pointer;
}

.elevator-car {
    height: 200px;
    width: 200px;
    background: red;
    position: absolute;
    margin: auto;
    transition: top .5s ease;
}
</style>
