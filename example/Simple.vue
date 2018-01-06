<template>
  <div>
    <h3>Line Progress {{percent}}%</h3>
    <div class="line-container">
      <v-line :percent="percent" stroke-width="4" :strokeColor="color"/>
    </div>
    <h3>Circle Progress {{percent}}%</h3>
    <div class="circle-container">
      <v-circle :percent="percent" stroke-width="6" stroke-linecap="round" :strokeColor="color"/>
    </div>
    <p>
      <button @click="changeData">Change State</button>
    </p>
  </div>
</template>

<script>
import {VCircle, VLine} from 'v-progress'

export default {
  components: {
    VCircle,
    VLine
  },
  data() {
    return {
      percent: 30,
      color: '#3FC7FA'
    }
  },
  methods: {
    changeData() {
      const colorMap = ['#3FC7FA', '#85D262', '#FE8C6A'];
      const value = parseInt(Math.random() * 100, 10);
      this.percent = value;
      this.color = colorMap[parseInt(Math.random() * 3, 10)];
    }
  }
}
</script>

<style scoped>
  .line-container{
    width: 250px;
  }
  .circle-container{
    width: 250px;
    height: 250px;
    display: inline-block;
  }
</style>

