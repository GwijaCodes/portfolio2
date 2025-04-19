<script setup>
import Nav from '@pages/components/Nav.vue'
import HeroSection from '@pages/HeroSection.vue'
import AboutSection from '@pages/AboutSection.vue'
import FeaturesSection from '@pages/FeaturesSection.vue'
import Projects from '@pages/Projects.vue'
import FooterSection from '@pages/FooterSection.vue'
</script>

<template>
  <Nav />
  <main class="home-wrapper">
    <HeroSection class="hero-fixed" />

    <div class="content">
      <AboutSection />
      <FeaturesSection />
      <Projects />
      <FooterSection />
    </div>
  </main>
</template>

<style>
@import "@/assets/style.css";

:root {
  --chiaro: #d9d9d9;
  --blu: #0056C6;
  --scurissimo: #151515;
  --giallo: #E49600;
}

main {
  width: 100%;
}

.home-wrapper {
  position: relative;
  overflow-x: hidden;
}

/* Hero section fissa */
.hero-fixed {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: 0;
}

.content {
  position: relative;
  z-index: 1;
  margin-top: 110vh;
}
</style>
