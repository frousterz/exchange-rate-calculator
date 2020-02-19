<template>
  <div class="is-fullwidth">
    <div class="container is-fullhd">
      <title-section />

      <section>
        <div class="columns is-centered mg__top">
          <div class="column is-6 text-centered">
            Choose the currency and the amounts to get the Exchange Rate
          </div>
        </div>
      </section>

      <section>
        <div class="container mg__top--50">
          <div class="columns  is-centered">
            <div class="column is-4">
              <b-field
                label="From"
                type="is-black">
                <div class="control has-icons-left">
                  <div class="select is-small">
                    <select id="from-select">
                      <option v-for="(rate, code) in info.rates" :key="rate.id" :class="code">{{code}}</option>
                    </select>
                  </div>
                  <span class="icon is-small is-left">
                    <b-icon icon="cash"></b-icon>
                  </span>
                </div>
              </b-field>
            </div>
            <div class="column is-4">
              <b-field label="Amount">
                <b-numberinput custom-class="amount" type="is-light" size="is-small" min="1" :value="1"></b-numberinput>
              </b-field>
            </div>
          </div>
        </div>

        <div class="container mg__top">
          <div class="columns is-centered">
            <div class="column is-8">
              <button class="button is-black" @click="swap()">swap</button>
            </div>
          </div>
        </div>

        <div class="container mg__top">
          <div class="columns  is-centered">
            <div class="column is-4">
              <b-field
                label="To"
                type="is-black">
                <div class="control has-icons-left">
                  <div class="select is-small second-select">
                    <select id="to-select">
                      <option v-for="(rate, code) in info.rates" :key="rate.id" :class="code">{{code}}</option>
                    </select>
                  </div>
                  <span class="icon is-small is-left">
                    <b-icon icon="cash"></b-icon>
                  </span>
                </div>
              </b-field>
            </div>

            <div class="column is-4" >
              <div>
                <label class="label">Result</label>
                <div class="tag is-small is-info result">1</div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import $ from 'jquery'
import TitleSection from '~/components/Title.vue'

export default {
  components: {
    TitleSection
  },
  data () {
    return {
      info: {
        base: "No Base",
        rates: {}
      },
      current: { }
    }
  },
  methods: {
    setData() {
      axios
        .get('https://api.exchangerate-api.com/v4/latest/USD')
        .then(response => (this.info = response.data))
    },
    updateFields(from, to) {
      return axios
        .get(`https://api.exchangerate-api.com/v4/latest/${from}`)
        .then(response => {
          this.response = response.data
          return this.response
        })
    },
    applyChange() {
      let vm = this
      vm.updateFields(
        $("#from-select option:selected" ).text(),
        $("#to-select option:selected" ).text()
      ).then(data => {
        $('.result')
          .html(
            $('.amount').val() *
            Math.round(parseFloat(
              data.rates[`${$("#to-select option:selected").text()}`]) * 100
            )/100
          )
      })
    },
    addEvents(){
      let vm = this
      $('#from-select, #to-select').change(function(e){
        vm.applyChange()
      })
      $(".amount").bind("change paste keyup", function() {
        vm.applyChange()
      })
      $('span.icon.is-small').click(function() {
        vm.applyChange()
      })
    },
    swap() {
      let vm = this
      let fromSelectedOption = $('#from-select').children('option:selected').text()
      let toSelectedOption = $('#to-select').children('option:selected').text()
      $('#from-select').children().removeAttr('selected')
      $(`#from-select option[class="${toSelectedOption}"]`).prop("selected", true)
      $('#to-select').children().removeAttr('selected')
      $(`#to-select option[class="${fromSelectedOption}"]`).prop("selected", true)

      // Update result
      vm.applyChange()
    }
  },
  mounted () {
    this.setData()
    this.addEvents()
  }
}
</script>

<style lang="scss" scoped>
.select {
  width: 100%;
  select {
    width: 100%;
  }
}

.result {
  width: 100%;
  font-size: 14px;
  font-weight: bold;
}
</style>
