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
  appearance: none;
  outline: none;
  border: none;
  background: none;

  position: absolute;
  top: 0;
  right: 0;
  margin-top: 10px;
  margin-right: 10px;

  cursor: pointer;

  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 17px;
  font-weight: 600;
  color: rgba(181, 215, 246, 0.597);
  transition: 0.4s;
  padding: 8px;
  border-radius: 2px;
}

#toggleBtn:hover {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
  backdrop-filter: blur(3px);
  border-radius: 5%;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
}
</style>