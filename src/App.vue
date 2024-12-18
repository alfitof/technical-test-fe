<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
</script>

<template>
  <div class="wrapper">
    <Header />
    <HeroSection />
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  border-radius: 0.5rem;
  flex-flow: column;
  margin: 0.75rem;
  display: flex;
  overflow: hidden;
}

@media (max-width: 1024px) {
  .wrapper {
    border-radius: 0rem;
    margin: 0rem;
  }
}
</style>
