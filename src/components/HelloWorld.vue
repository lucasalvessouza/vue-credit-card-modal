<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <button
      type="button"
      class="btn"
      @click="showModal"
    >
      Open Modal!
    </button>
    <modal-credit-card v-show="openModal" @close="closeModal"></modal-credit-card>
  </div>
</template>

<script>
import ModalCreditCard from '../components/ModalCreditCard'

export default {
  name: 'HelloWorld',
  data() {
    return {
      openModal: false
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
