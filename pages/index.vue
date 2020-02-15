<template>
  <div class="hero is-dark is-fullheight-with-navbar">
    <vue-particles
        color="#dedede"
        :particleOpacity="0.7"
        :particlesNumber="20"
        shapeType="circle"
        :particleSize="4"
        linesColor="#ffffff"
        :linesWidth="1"
        :lineLinked="true"
        :lineOpacity="0.4"
        :linesDistance="150"
        :moveSpeed="3"
        :hoverEffect="true"
        hoverMode="grab"
        :clickEffect="true"
        clickMode="push"
      >
      </vue-particles>
      <fields-section />
      <tech />
  </div>
</template>

<script>
import FieldsSection from '~/components/FieldsSection.vue'
import Tech from '~/components/Tech.vue'

export default {
  components: {
    FieldsSection,
    Tech
  }
}
</script>

