<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">click me</button> -->
  <p>welcome...</p>
  <div v-if="showModal">
    <Modal aHardCodedAttribute="a hard coded attribute value" 
      v-bind:header="modalHeader" :text="modalText" theme="sale" 
      @close="toggleModal">
      <template v-slot:links>
        <a href="#">nameed slot template1</a>
      </template>
      <template v-slot:links2>
        <a href="#">nameed slot template2</a>
      </template>
      <p>default slot template given by this component, the parent componet to Modal.vue</p>
    </Modal>
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)',
      modalHeader: 'Sign up for the giveaway!',
      modalText: 'Grab your ninja swag for half price',
      showModal: false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()

      this.$data.title = 'aaaaa'
      this.title = 'bbbbb'
    },
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

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
