
<template>
  <b-navbar type="is-black" :fixed-top=true>
      <template slot="brand">
          <b-navbar-item tag="router-link" :to="{ path: '/' }">
              Exchange Rate Calculator
          </b-navbar-item>
      </template>

      <template slot="end">
        <b-navbar-item tag="div">
            <div class="buttons">
                <button class="button is-info">
                  <b-icon icon="github-circle"></b-icon>
                    <span>Github</span>
                </button>
                <button class="button is-success">
                    <b-icon icon="download"></b-icon>
                    <span>Download</span>
                </button>
            </div>
        </b-navbar-item>
      </template>
  </b-navbar>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
</style>

