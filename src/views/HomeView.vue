<template>
  <div class="home">
    <!--<img alt="Vue logo" src="../assets/logo.png"> -->
    <ClockApp />
    <WeatherPanel />
    <ParticleBackgrund />
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
  }
}
</script>
