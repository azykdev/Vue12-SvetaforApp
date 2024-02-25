<template>
  <div class="inputDiv">
    <input type="number" v-model="getNum">
    <h1>{{ getNum }}</h1>
  </div>
  <div style="display: flex; align-items: center; justify-content: center; flex-wrap: wrap;">
    <TrafficLight v-for="n in getNum" :randomNum="randomNum()" />
  </div>
</template>

<script>
import TrafficLight from './components/TrafficLight.vue';

export default {
  name: 'App',
  components: { TrafficLight },
  data() {
    return {
      getNum: 0
    }
  },
  methods: {
    randomNum() {
      return Math.floor(Math.random() * 10)
    }
  },
}
</script>

<style scoped>
.inputDiv {
  width: 30%;
  margin: 20px auto;
  text-align: center;
}

input {
  width: 100%;
  padding: 10px;
}
</style>