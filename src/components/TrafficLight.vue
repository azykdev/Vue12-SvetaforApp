<template>
  <div class="svetofor">
    <div class="chiroq" :class="[second > 0 && second < 5 ? 'red' : '']"></div>
    <div class="chiroq" :class="[(second > 5 && second < 8) || (second > 12 && second < 15) ? 'yellow' : '']"></div>
    <div class="chiroq" :class="[second > 8 && second < 12 ? 'green' : '']"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      second: 0,
    }
  },
  props: {
    randomNum: Number
  },
  methods: {
    secundomer() {
      setInterval(() => {
        this.second++
        if (this.second == 15) this.second = 0
      }, 1000)
    },
    timer() {
      setTimeout(() => {
        console.log(this.mlSecond);
        this.secundomer()
      }, this.mlSecond)
    }
  },
  computed: {
    mlSecond() {
      return this.randomNum * 1000
    }
  },
  mounted() {
    this.timer()
  }
}
</script>

<style scoped>
.svetofor {
  background: #000;
  display: inline-block;
  padding: 20px;
  margin: 5px;
  border-radius: 10px;

}

.chiroq {
  width: 100px;
  height: 100px;
  background: #333;
  border-radius: 50%;
  margin-bottom: 10px;
}

.red {
  background: red;
}

.yellow {
  background: yellow;
}

.green {
  background: green;
}
</style>