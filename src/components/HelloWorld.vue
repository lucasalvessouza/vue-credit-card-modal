<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div>{{ card }}</div>
    <button type="button" class="btn" @click="showModal">Open Modal!</button>
    <modal-credit-card v-show="openModal" @close="closeModal" @card="saveCard"></modal-credit-card>
  </div>
</template>

<script>
import ModalCreditCard from '../components/ModalCreditCard'

export default {
  name: 'HelloWorld',
  data() {
    return {
      openModal: false,
      card: {
        number: null,
        holderName: null,
        expirationMonth: null,
        expirationYear: null,
        cvv: null,
        brand: null
      }
    }
  },
  components: {
    ModalCreditCard
  },
  props: {
    msg: String
  },
  methods: {
    closeModal() {
      this.openModal = false
    },
    showModal() {
      this.openModal = true
    },
    saveCard(card) {
      this.card = card
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
