<template>
  <div class="is-fullwidth">
    <div class="container is-fullhd">
      <title-section />
      <section>
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
              <button class="button is-black">swap</button>
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
  </div>
</template>

<script>
import TitleSection from '~/components/Title.vue'

export default {
  components: {
    TitleSection
  }
}
</script>

<style lang="scss" scoped>
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

