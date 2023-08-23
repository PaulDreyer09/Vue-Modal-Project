<template>
  <div>
    <h1>{{ title }}</h1>
    <ModalView :header="header" :text="text" theme="sale"/>
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
    return{
      title: 'My First Vue App',
      header: "Sign up for the Giveaway!",
      text: 'Grab your ninja swag for half price!',
    }
  },
  methods: {

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
