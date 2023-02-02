<template>
  <div class="home">
    <!--<img alt="Vue logo" src="../assets/logo.png"> -->
    <ClockApp />
    <ParticleBackgrund />
  </div>
</template>

<script>
// @ is an alias to /src
import ParticleBackgrund from '@/components/ParticleBackground.vue';
import ClockApp from '@/components/ClockApp.vue'

export default {
  name: 'HomeView',
  components: {
    ParticleBackgrund,
    ClockApp
  }
}
</script>
