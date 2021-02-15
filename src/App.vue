<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :message="message" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click="toggleModal">Show Modal</button>
  <!--<input type="text" ref="name" />
  <button @click="handleClick">Click</button>-->
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'First Vue app',
      message: 'This is a prop',
      text: 'Prop text',
      showModal: false
    }
  },
  methods: {
    /*handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus();
    }*/
    toggleModal() {
      this.showModal = !this.showModal
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
