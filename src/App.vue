<template>
  <h1>{{title}}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <div>
    <input type="text" ref="select" >
  </div>  
  <button @click="handleClick">Click Me</button>
  <button @click ="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{ Modal },
  data() {
    return {
      title: ' My First Vue App',
      header: 'Sign Up Now',
      text: 'Remember Me',
      showModal:false
    }
  },

  methods: {
    handleClick() {
      console.log(this.$refs.select)
      this.$refs.select.classList.add('active')
      this.$refs.select.focus() 
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
h1{
  border-bottom: 1px solid #2c3e50;
  color:#ddd ;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
