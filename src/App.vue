<template>
  <h1> {{title}} </h1>
  <h3> Welcome... </h3>
  <teleport to ='.modals' v-if='showModal'>
  <Modal theme= '' @close='showModal=false'>
    <template v-slot:links>
      <a href='#'> Click here to sign up now </a>
      <a href='#'> Click here for more info </a>
    </template>
    <h1> Welcome to my world </h1>
    <p> My lord </p>
  </Modal>
  </teleport>
  
  <teleport to='.modals' v-if='showModalTwo'>
  <Modal @close='showModalTwo=false'>
    <h1> Sign up to the newsletter </h1>
    <p> For updates and promo codes  </p>
  </Modal>
  </teleport>

  <button @click = 'toggleModal'> Open first </button>
  <button @click = 'toggleModalTwo'> Open second </button>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
    data () {
      return {
        title: 'My first Vue App :)',
        showModal: false,
        showModalTwo: false
      }
    },
    methods:{
      toggleModal(){
        this.showModal = !this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
    }
}

</script>

<style>
#app,.modals {
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

  button{
  background-color: rgb(21, 17, 224);
  color: white;
  padding: 5px 20px;
  cursor: pointer;
  margin:10px auto;
  border-radius: 5%;
  display:block;
}

</style>
