<script lang="ts" setup>
import Hero from "@/components/Hero.vue";
import Services from "@/components/Services.vue";
import Testimonials from "@/components/Testimonials.vue";
import AboutUs from "@/components/AboutUs.vue";
import Contact from "@/components/Contact.vue";
import FAQ from "@/components/FAQ.vue";

import type {Container} from "@tsparticles/engine";
import {Options} from "tsparticles-engine";

const options: Options = {
  particles: {
    number: {
      value: 30
    },
    color: {
      value: "#c2c2c2"
    },
    links: {
      enable: true,
      distance: 250,
      color: "#c2c2c2",
      opacity: 0.4,
      width: 2
    },
    shape: {
      type: "circle"
    },
    opacity: {
      value: 1
    },
    size: {
      value: {
        min: 4,
        max: 6
      }
    },
    move: {
      enable: true,
      speed: 2
    }
  },
  background: {
    color: "transparent"
  },
  interactivity: {
    events: {
      onclick: {
        enable: true,
        mode: "push"
      },
      resize: true
    }
  },
  retina_detect: true,
  fullscreen: {
    enable: false // Particles will not cover the entire page
  },
  zIndex: {
    value: -1 // Ensure particles are behind other content
  }
};


// Load particles asynchronously
const particlesLoaded = async (container: Container) => {
  console.log(container);
};
</script>

<template>
  <div id="sections">
    <!-- Particles only in Hero section -->
    <div id="particles-js-hero">
      <vue-particles :options="options" @particles-loaded="particlesLoaded"/>
    </div>
    <Hero/>


    <AboutUs/>
    <div>
      <Services/>
    </div>
    <div>
      <Testimonials/>
    </div>
    <Contact/>
    <div>
      <FAQ/>
    </div>
  </div>
</template>

<style scoped>

#sections {
  position: relative;
  z-index: 2;
}

#particles-js-hero {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -5;
}


body, html {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  height: 100%;
}
</style>
