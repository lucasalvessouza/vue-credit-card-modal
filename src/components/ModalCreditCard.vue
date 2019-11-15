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
            <VForm />
          </slot>
        </section>
        <!-- <footer class="modal-footer">
          <slot name="footer">
            <div class="modal-footer__right">
              <button
                type="button"
                class="btn"
                @click="close"
                aria-label="Close modal"
              >
                Salvar
              </button>
              <button
                type="button"
                class="btn"
                @click="close"
                aria-label="Close modal"
              >
                Salvar
              </button>
            </div>
          </slot>
        </footer> -->
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
        month: '',
        year: '',
        cvv: ''
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
