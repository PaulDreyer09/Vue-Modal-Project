<template>
  <h1>{{ title }}</h1>
  <button @click="toggleModal">
    <span v-if="showModal">Hide Modal</span>
    <span v-else>Show Modal</span>
  </button>
  <button @click="toggleModalTwo">
    <span v-if="showModalTwo">Hide Modal Two</span>
    <span v-else>Show Modal Two</span>
  </button>
  <div v-if="showModal">
    <ModalView theme="" @close="toggleModal">
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>

      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">Not yet</a>
      </template>
    </ModalView>    
  </div>
  <div v-if="showModalTwo">
      <ModalView theme="sale" @close="toggleModalTwo">
        <h1>Did you remember to subscribe?</h1>
        <p>You know what to do!</p>

        <template v-slot:links>
          <a href="#">Yes</a>
          <a href="#">No</a>
          <a href="#">Wait what?</a>
        </template>
      </ModalView>
    </div>
</template>



<script>
import ModalView from "./components/ModalView";

export default {
  name: 'App',
  components: {
    ModalView
  },
  data() {
    return {
      title: 'My First Vue App',
      header: "Sign up for the Giveaway!",
      text: 'Grab your ninja swag for half price!',
      showModal: false,
      showModalTwo: false,

    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
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
