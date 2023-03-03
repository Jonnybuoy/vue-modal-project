<template>
  <h1>{{ title }}</h1>
  <p>Welcome ..</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign here</a>
        <a href="#">More Info</a>
      </template>
      <h1>Sign up for the giveaway!</h1>
      <p>Grab your ninja swag now1</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal theme="" @close="toggleModalTwo">
      <template v-slot:links>
        <a href="#">Sign here</a>
        <a href="#">More Info</a>
      </template>
      <h1>Here We Are!</h1>
      <p>Grab your ninja swag now1</p>
    </Modal>
  </div>
  <button @click.shift="toggleModal">open modal (shift-click)</button>
  <button @click="toggleModalTwo">open modal two (alt-click)</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first Vue App :)',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
