<template>
  <div>
    <div class="circle-contianer">
      <v-circle
        :percent="percent"
        :gapDegree="70"
        gapPosition="top"
        :strokeWidth="6"
        strokeLinecap="square"
        :strokeColor="color"
      />
    </div>
    <div class="circle-contianer">
      <v-circle
        :percent="percent"
        :gapDegree="70"
        gapPosition="bottom"
        :strokeWidth="6"
        strokeLinecap="square"
        :strokeColor="color"
      />
    </div>
    <div class="circle-contianer">
      <v-circle
        :percent="percent"
        :gapDegree="70"
        gapPosition="left"
        :strokeWidth="6"
        strokeLinecap="square"
        :strokeColor="color"
      />
    </div>
    <div class="circle-contianer">
      <v-circle
        :percent="percent"
        :gapDegree="70"
        gapPosition="right"
        :strokeWidth="6"
        strokeLinecap="square"
        :strokeColor="color"
      />
    </div>
    <p>
      <button @click="changeData">Change State</button>
    </p>
  </div>
</template>

<script>
import {VCircle} from 'v-progress'

export default {
  components: {
    VCircle
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
  .circle-contianer{
    width: 200px;
    height: 200px
  }
</style>

