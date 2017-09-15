<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <router-view></router-view>
    <image-modal :visible="true" transition="roll">
      <p class="image is-4by3">
        <img src="http://placehold.it/1280x960">
      </p>
    </image-modal>
    <card-modal :visible="true" :title="title" transition="zoom">
      <div class="content has-text-centered">
        <img :src="src" height="120" alt="Vue Admin">
      </div>
    </card-modal>
  </div>
</template>

<script>
import { Modal, ImageModal, CardModal } from 'vue-bulma-modal'
import BaseModal from './components/BaseModal'
export default {
  name: 'app',
  mixins: [BaseModal],
  data () {
    return {
      title: '提示',
      src: 'http://placehold.it/1280x960'
    }
  },
  props: {
    closable: {
      type: Boolean,
      default: true
    }
  },
  components: {
    Modal,
    ImageModal,
    CardModal
  },
  computed: {
    classes () {
      return ['modal', 'animated', 'is-active']
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
</style>
