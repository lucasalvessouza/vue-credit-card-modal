<template>
  <div class="card-form__row">
    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <div class="cc-header card-form__row">
            <div class="card-form__col float-left">
              <img src="@/assets/img/chip.png" width="45" />
            </div>
            <div class="card-form__col float-right">
              <img src="@/assets/img/brands/master-card.png" width="70" />
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
    }
  }
}
</script>

<style lang="scss"></style>
