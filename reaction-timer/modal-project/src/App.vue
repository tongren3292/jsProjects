<template>
  <h1>{{title}} </h1>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
  <p>Welcome...</p>
  <div v-if="showModal">

    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway</h1>
      <p>Grab your ninja swag at half price</p>
    </Modal>

  </div>
  
  <div v-if="showModalTwo">

    <Modal @close="toggleModalTwo">
      <h1>sign up to news</h1>
      <p>for updates and codes</p>
    </Modal>

  </div>
  <button @click="toggleModal">Show Modal</button>
  <button @click="toggleModalTwo">Show Modal2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  data(){
    return{
      title: 'my first vue app',
      showModal: false,
      showModalTwo: false
    }
  },

  methods:{
      handleClick(){
          console.log(this.$refs.name)
          this.$refs.name.classList.add('active')
          this.$refs.name.focus()
      },
      toggleModal(){
        this.showModal = !this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
  },

  components:{
    Modal
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
