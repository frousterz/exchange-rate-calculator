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

<style lang="scss">
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

.mg{
  &__top{
    margin-top: 20px;
    &--50 {
      margin-top: 50px;
    }
  }

  &__bt{
    &--20 {
      margin-top: 20px;
      margin-bottom: 20px;
    }
  }
}
</style>
