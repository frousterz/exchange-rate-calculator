<template>
  <div>
    <navbar />
    <nuxt class="content"/>
  </div>
</template>

<script>
import Vue from 'vue'
import VueParticles from 'vue-particles'
Vue.use(VueParticles)

import Navbar from '~/components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>

<style>
.label {
  color: #fff !important;
}

.text-centered {
  text-align: center;
}

.text-large{
  font-size: 70px;
}

#particles-js {
  position: fixed;
  width: 100vw;
  height: 100vh;
}

.columns {
  padding: 0;
  margin: 0;
}
</style>
