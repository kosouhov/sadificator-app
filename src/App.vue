<template>
  <div id="app">
    <Upload
      @chooseImage="changeFile"
    />
    <img :src="image" />
  </div>
</template>

<script>
import Upload from './components/Upload.vue'

export default {
  name: 'app',
  components: {
    Upload
  },
  data () {
    return {
      image: ''
    }
  },
  methods: {
    changeFile: function(e) {
      let files = e.target.files || e.dataTransfer.files
      if (files.length) {
        this.createImage(files[0])
      }
    },
    createImage(file) {
      let image = new Image(),
        reader = new FileReader(),
        o = this
      reader.onload = (e) => {
        o.image = e.target.result;
      };
      reader.readAsDataURL(file);
    }
  }
}
</script>

<style lang="sass">
  @import './sass/style.sass'
</style>