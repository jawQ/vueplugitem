<template>
<div class="">
  <image-modal :visible="true" transition="roll">
     <p class="image is-4by3">
       <img :src="src">
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
import BaseModal from './BaseModal'
import ImageModal from './ImageModal'
import CardModal from './CardModal'
export default {
  data () {
    return {
      title: '同标题',
      src: 'http://placehold.it/1280x960'
    }
  },
  mixins: [BaseModal],
  props: {
    closable: {
      type: Boolean,
      default: true
    }
  },
  computed: {
    classes () {
      return ['modal', 'animated', 'is-active']
    }
  },
  components: {
   ImageModal,
   CardModal
 }
}
</script>
