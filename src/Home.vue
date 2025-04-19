<template>
  <main class="flex flex-col items-center">
    <Nav />
    <HeroSection />
    <FeaturesSection />
    <AboutSection />
    <Projects />
    <FooterSection />
  </main>
</template>

<script setup>
import Nav from '@pages/components/Nav.vue'
import HeroSection from '@pages/HeroSection.vue'
import AboutSection from '@pages/AboutSection.vue'
import FeaturesSection from '@pages/FeaturesSection.vue'
import Projects from '@pages/Projects.vue'
import FooterSection from '@pages/FooterSection.vue'
</script>

<style scoped>
main {
  width: 100%;
}
</style>