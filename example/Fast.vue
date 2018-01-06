<template>
  <div class="container">
    <v-circle :percent="percent" :strokeWidth="6" />
    <v-line :strokeWidth="4" :percent="percent" />
    <p>
      <button @click="restart">Restart</button>
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
      percent: 0
    }
  },
  mounted() {
    this.increase()
  },
  methods: {
    increase() {
      const percent = this.percent + 1;
      if (percent >= 100) {
        clearTimeout(this.tm);
        return;
      }
      this.percent = percent;
      this.tm = setTimeout(this.increase, 10);
    },
    restart() {
      clearTimeout(this.tm);
      this.percent = 0;
      this.$nextTick(this.increase)
    }
  }
}
</script>

<style scoped>
  .container{
    width: 200px
  }
  .circle-contianer{
    width: 200px;
    height: 200px
  }
</style>

