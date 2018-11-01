<template>
  <div id="app">
    <Upload
      v-if="upload_mode"
      @chooseImage="changeFile"
      @buttonClick="sadificate"
      :message="message"
      :button="button"
    />
    <Photo
      v-else
      :image="image"
    />
    <audio id="audio">
      <source :src="require('./assets/sound.ogg')">
      <source :src="require('./assets/sound.mp3')">
    </audio>
  </div>
</template>

<script>
import Upload from './components/Upload.vue'
import Photo from './components/Photo.vue'

export default {
  name: 'app',
  components: {
    Upload,
    Photo
  },
  data () {
    return {
      upload_mode: true,
      image: '',
      message: 'Upload your photo',
      button: false
    }
  },
  methods: {
    changeFile: function(e) {
      let files = e.target.files || e.dataTransfer.files
      if (files.length) {
        if (files[0].type.indexOf('image') >= 0) {
          this.createImage(files[0])
          this.message = files[0].name.length > 16 ? files[0].name.slice(0, 13) + '...' : files[0].name
          this.button = true
        } else {
          this.message = 'Wrong file type'
          this.button = false
        }
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
    },
    sadificate: function() {
      document.getElementById('audio').play()
      this.upload_mode = false
    }
  }
}
</script>

<style lang="sass">
  @import './sass/style.sass'
</style>