<template>
  <div id="about" class="about">
    <h1>About</h1>
    <div class="text">
      This site was built as a VueJS learning project <br>
      It uses Vue 3, tsParticles and the OpenWeather API to fetch the weather data.
    </div>
  </div>
  <ParticleBackground />
</template>

<style>
.about {
  color: rgba(181, 215, 246, 0.597);
  background: linear-gradient(135deg,
      rgba(255, 255, 255, 0.1),
      rgba(255, 255, 255, 0));
  backdrop-filter: blur(3px);
  border-radius: 5%;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
  width: max-content;
  margin: auto;
  padding-bottom: 30px;
  padding-left: 10px;
  padding-right: 10px;
}
.text {
  font-size: 30px;
  white-space: pre-line;
}
h1 {
  color: #B2CFCF;
}
</style>

<script>
import ParticleBackground from "@/components/ParticleBackground.vue";

export default {
  components: {
    ParticleBackground,
  },
};
</script>
