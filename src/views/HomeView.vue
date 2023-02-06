<template>
  <div class="home">
    <button id="toggleBtn" @click="toggleBackground">Toggle Animation</button>
    <ClockApp />
    <WeatherPanel />
    <ParticleBackgrund v-if="enableAnimation" />
    <div class="background" v-else></div>
  </div>
</template>

<script>
// @ is an alias to /src
import ParticleBackgrund from '@/components/ParticleBackground.vue';
import ClockApp from '@/components/ClockApp.vue'
import WeatherPanel from '@/components/WeatherPanel.vue';

export default {
  name: 'HomeView',
  components: {
    ParticleBackgrund,
    ClockApp,
    WeatherPanel
  },
  data() {
    return {
      enableAnimation: true
    }
  },
  methods: {
    toggleBackground() {
      this.enableAnimation = !this.enableAnimation
    }
  }
}
</script>

<style>
.background {
  position: fixed;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  z-index: -100;
  background-color: #1E1E1E;
}

#toggleBtn {
  position: absolute;
  top: 0;
  right: 0;
  margin-top: 10px;
  margin-right: 10px;
}
</style>