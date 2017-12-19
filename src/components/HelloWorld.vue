<template>
  <div class="hello">
      <div class="container">
      <h2>Upload file</h2>
      <vue-base64-file-upload 
        class="v1"
        accept="image/png,image/jpeg"
        image-class="v1-image"
        input-class="v1-image"
        :max-size="customImageMaxSize"
        @size-exceeded="onSizeExceeded"
        @file="onFile"
        @load="onLoad" />
    </div>
  </div>
</template>

<script>
import VueBase64FileUpload from 'vue-base64-file-upload';
export default {
  name: 'HelloWorld',
  components: {
    VueBase64FileUpload
  },
  data () {
    return {
      customImageMaxSize: 3
    };
  },
  methods: {
    onFile(file){
      console.log(file);
    },
    onLoad(dataUri){
      console.log(dataUri);
    },
    onSizeExceeded(size){
      alert(`Image ${size}Mb size exceeds limits of ${this.customImageMaxSize}Mb!`);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
