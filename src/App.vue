<template>
  <h1>
{{ title }}  
</h1>
<p>Welcome...</p>
<teleport to=".modals" v-if="showModal">
  <Modal @close="toggleModal">
<template v-slot:links>
  <a href="#">sign up now</a>
  
  <a href="#">more info</a>

</template>
      
<h1>
Ninja Giveaway!
</h1>
<p>
Grab your ninja swag for half price!
</p>
  </Modal>
</teleport>
<button @click.alt="toggleModal">Open Modal (alt) </button>
<teleport to=".modals" v-if="showSecondModal">
<Modal @close="toggleSecondModal">
<h1>Great man</h1>
<p>ikan ti yato ni time yii, wo tin wo mi pelu oju mii</p>

</Modal>
</teleport>
<button @click.shift="toggleSecondModal"> Another Modal (shift)</button>
</template>

<script>
import Modal from './components/Modal.vue';


export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return {
      title: 'My first vue app',
      showModal: false,
      showSecondModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleSecondModal(){
      this.showSecondModal = !this.showSecondModal
    }
  }
}
</script>

<style>
#app, .modals {
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
