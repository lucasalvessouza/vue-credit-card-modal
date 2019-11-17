<template>
  <div>
    <VCard :card="card" :flipCard="flipCard" />
    <div class="card-form">
      <div class="card-form__inner">
        <div class="card-input">
          <label class="card-input__label">Credit card number</label>
          <input
            type="text"
            class="card-input__input"
            v-model="card.number"
            v-mask="'#### #### #### ####'"
          />
        </div>
        <div class="card-input">
          <label class="card-input__label">Holder name</label>
          <input type="text" class="card-input__input" v-model="card.holderName" />
        </div>
        <div class="card-form__row">
          <div class="card-form__col">
            <div class="card-form__group">
              <label class="card-input__label">Expiration date</label>
              <select name id class="card-input__input -select" v-model="card.expirationMonth">
                <option v-for="(index, key) in 12" :key="key">{{ index }}</option>
              </select>

              <select name id class="card-input__input -select" v-model="card.expirationYear">
                <option>2020</option>
                <option>2021</option>
                <option>2022</option>
                <option>2023</option>
              </select>
            </div>
          </div>
          <div class="card-form__col">
            <div class="card-input">
              <label class="card-input__label">CVV</label>
              <input
                type="text"
                class="card-input__input"
                v-model="card.cvv"
                maxlength="4"
                @focus="flipCard = true"
                @blur="flipCard = false"
              />
            </div>
          </div>
        </div>
        <div class="card-form__row">
          <div class="card-form__footer">
            <button type="button" class="btn" aria-label="Close modal" @click="saveCard">Salvar</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VCard from './VCard'

export default {
  props: {
    card: {
      type: Object,
      required: true
    }
  },
  components: {
    VCard
  },
  data() {
    return {
      flipCard: false
    }
  },
  methods: {
    saveCard() {
      this.$emit('saveCard', this.card)
    }
  },
}
</script>
