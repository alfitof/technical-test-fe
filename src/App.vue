<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import Footer from './components/Footer.vue'
import VacanciesSection from './components/VacanciesSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import HorizontalSlider from './components/HorizontalSlider.vue'
import MemberSection from './components/MemberSection.vue'
import Vacancies1Section from './components/Vacancies1Section.vue'
import GalleryGridSection from './components/GalleryGridSection.vue'
</script>

<template>
  <div class="wrapper">
    <Header />
    <HeroSection />
    <AboutSection />
    <GalleryGridSection />
    <MemberSection />
    <HorizontalSlider />
    <ExperienceSection />
    <Vacancies1Section />
    <VacanciesSection />
    <Footer />
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
