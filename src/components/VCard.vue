<template>
  <div class="card-form__row">
    <div class="flip-card" :class="{ active: flipCard }">
      <div class="flip-card-inner">
        <!-- Card front -->
        <div class="flip-card-front">
          <div class="cc-header card-form__row">
            <div class="card-form__col float-left">
              <img src="@/assets/img/chip.png" width="45" />
            </div>
            <div class="card-form__col float-right">
              <img
                :src="require(`@/assets/img/brands/${card.brand}.png`)"
                width="70"
                v-if="card.brand"
              />
            </div>
          </div>

          <div class="cc-number card-form__row">
            <p>{{ card.number }}</p>
          </div>

          <div class="cc-footer card-form__row">
            <div class="card-form__col cc-holder">
              <p>Holder name</p>
              <label>{{ card.holderName }}</label>
            </div>
            <div class="card-form__col cc-expiration">
              <p>Validity</p>
              <label
                >{{ card.expirationMonth }}/{{ card.expirationYear }}</label
              >
            </div>
          </div>
        </div>

        <!-- Card back -->
        <div class="flip-card-back">
          <div class="cc-target card-form__row"></div>
          <div class="cc-info card-form__row">
            <div class="card-form__col float-right">
              <p>{{ card.cvv }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required: true
    },
    flipCard: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    getCardType() {
      let number = this.card.number
      if (number) {
        let re = new RegExp('^4')
        if (number.match(re) != null) return 'visa'

        re = new RegExp('^(34|37)')
        if (number.match(re) != null) return 'amex'

        re = new RegExp('^5[1-5]')
        if (number.match(re) != null) return 'mastercard'

        re = new RegExp('^6011')
        if (number.match(re) != null) return 'discover'

        re = new RegExp('^62')
        if (number.match(re) != null) return 'unionpay'

        re = new RegExp('^9792')
        if (number.match(re) != null) return 'troy'

        re = new RegExp('^3(?:0([0-5]|9)|[689]\\d?)\\d{0,11}')
        if (number.match(re) != null) return 'dinersclub'

        re = new RegExp('^35(2[89]|[3-8])')
        if (number.match(re) != null) return 'jcb'
      }
      return ''
    }
  },
  watch: {
    card: {
      handler(val) {
        this.card = val
        this.card.brand = this.getCardType()
      },
      deep: true
    }
  }
}
</script>

<style lang="scss"></style>
