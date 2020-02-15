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
  </div>
</template>

<script>
import FieldsSection from '~/components/FieldsSection.vue'

export default {
  components: {
    FieldsSection
  }
}
</script>

