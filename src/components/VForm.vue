<template>
  <div>
    <VCard />
    <div class="card-form">
      <div class="card-form__inner">
        <div class="card-input">
          <label class="card-input__label">Credit card number</label>
          <input type="text" class="card-input__input" />
        </div>
        <div class="card-input">
          <label class="card-input__label">Holder name</label>
          <input type="text" class="card-input__input" />
        </div>
        <div class="card-form__row">
          <div class="card-form__col">
            <div class="card-form__group">
              <label class="card-input__label">Expiration date</label>
              <select name="" id="" class="card-input__input -select">
                <option v-for="(index, key) in 12" :key="key">
                  {{ index }}
                </option>
              </select>

              <select name="" id="" class="card-input__input -select">
                <option value="">2020</option>
                <option value="">2021</option>
                <option value="">2022</option>
                <option value="">2023</option>
              </select>
            </div>
          </div>
          <div class="card-form__col">
            <div class="card-input">
              <label class="card-input__label">CVV</label>
              <input type="text" class="card-input__input" />
            </div>
          </div>
        </div>
        <div class="card-form__row">
          <div class="card-form__footer">
            <button type="button" class="btn" aria-label="Close modal">
              Salvar
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VCard from './VCard'
export default {
  components: {
    VCard
  }
}
</script>
