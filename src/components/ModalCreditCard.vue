<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div
        class="modal"
        role="dialog"
        aria-labelledby="modalTitle"
        aria-describedby="modalDescription"
      >
        <header class="modal-header" id="modalTitle">
          <slot name="header">
            <div class="modal-header__title">
              Add card title
            </div>
            <button
              type="button"
              class="close"
              @click="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">×</span>
            </button>
          </slot>
        </header>
        <section class="modal-body" id="modalDescription">
          <slot name="body">
            <VForm :card="card" />
          </slot>
        </section>
      </div>
    </div>
  </transition>
</template>

<script>
import VForm from './VForm'

export default {
  name: 'modal-credit-card',
  data() {
    return {
      card: {
        number: null,
        holderName: null,
        expirationMonth: 2,
        expirationYear: 2022,
        cvv: null
      }
    }
  },
  components: {
    VForm
  },
  methods: {
    close() {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss"></style>
