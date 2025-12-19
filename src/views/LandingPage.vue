<template>
  <div class="landing-page">
    <Navbar />
    <HeroSection />
    <FeaturesSection />
    <HowItWorksSection />
    <ServicesSection />
    <FooterSection />
  </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
import HeroSection from '../components/HeroSection.vue'
import FeaturesSection from '../components/FeaturesSection.vue'
import HowItWorksSection from '../components/HowItWorksSection.vue'
import ServicesSection from '../components/ServicesSection.vue'
import FooterSection from '../components/FooterSection.vue'
</script>

<style scoped>
.landing-page {
  width: 100%;
  overflow-x: hidden;
}
</style>
