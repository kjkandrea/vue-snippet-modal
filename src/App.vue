<template>
  <div id="app">
    {{ msg }}
    <div>
      <button @click="onClickOpen">Open</button>
    </div>
    <transition name="modal"  v-if="showModal">
      <div class="modal-mask">
        <modal @close="modalToggle">
          <h3 slot="header">Modal</h3>
          <div slot="body">안녕하세요. 저는 모달입니다.</div>
        </modal>
      </div>
    </transition>
  </div>
</template>

<script>
import Modal from './components/ModalElement';

export default {
  components: {
    Modal
  },
  name: 'app',
  data () {
    return {
      msg: 'Welcome to My Vue.js Snippet',
      showModal: false
    }
  },
  methods: {
    onClickOpen() {
      this.modalToggle()
    },
    modalToggle() {
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
