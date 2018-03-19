<template>
  <div id="translateForm">
      <form v-on:submit="formSubmit">
          <!-- binding this to the data at export by using v-model -->
          <input type = "text" v-model="textToTranslate" placeholder="Enter a word">
          <input type ="submit" value="Translate">
      </form>
  </div>
</template>

<script>
// 13:33
export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate: ''
      }
  },
  methods: {
      formSubmit(e) {
          alert('Submitted');
        e.preventDefault();
      }
  }
}
</script>

<style>

</style>
