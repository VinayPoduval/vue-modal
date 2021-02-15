<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :message="message" :text="text" theme="sale" @close="toggleModal">
      <h1>This is a Modal</h1>
      <p>Some default text</p>
      <template v-slot:links>
        <a href="#">Signup</a>
        <a href="#">Login</a>
      </template>
    </Modal>
  </div>
  <div v-if="showModal2">
    <Modal theme="sale" @close="toggleModal2">
      <h1>This is another Modal</h1>
      <p>Some more default text</p>
      <template v-slot:links>
        <a href="#">Modal2</a>
        <a href="#">Modal2</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Show Modal</button><br><br>
  <button @click="toggleModal2">Show Modal 2</button>
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
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    /*handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus();
    }*/
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
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
