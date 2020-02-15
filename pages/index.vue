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

    <section>
      <div class="is-fullwidth">
        <div class="container is-fullhd">
          <br><br>
          <div class="text-centered">
            <h1 class="title title--big">Exchange Rate Calculator</h1>
            This is a simple project using NuxtJs, Buefy, Axios and the ExchangeRate API.
          </div>
        </div>
      </div>

      <div class="container mg__top--50">
        <div class="columns">
          <div class="column is-4">
            <b-field
              label="From"
              type="is-black">
              <b-select placeholder="Select a currency" expanded icon="cash">
                <option value="flint">Flint</option>
                <option value="silver">Silver</option>
              </b-select>
            </b-field>
          </div>
          <div class="column is-4">
            <b-field label="Amount">
              <b-numberinput type="is-light"></b-numberinput>
            </b-field>
          </div>
        </div>
      </div>

      <div class="container mg__top">
        <div class="columns">
          <div class="column is-4">
            <button class="button is-primary">swap</button>
          </div>
        </div>
      </div>

      <div class="container mg__bt--20">
        <div class="columns">
          <div class="column is-4">
            <b-field
              label="To"
              type="is-black">
              <b-select placeholder="Select a character" expanded icon="cash">
                <option value="flint">Flint</option>
                <option value="silver">Silver</option>
              </b-select>
            </b-field>
          </div>
          <div class="column is-4">
            <b-field
              label="Result"
              type="is-black text-centered">
                <b-input
                  value="0000"
                >
                </b-input>
            </b-field>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  components: {
  }
}
</script>

<style lang="scss" scoped>
  .title {

    &--big {
      font-size: 5vw;
    }
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
