<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered By Vue.js</h5>
    <!-- onsubmit runs translate text method made below -->
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';

export default {
  name: 'App',
  components: {
    TranslateForm
  },
  methods: {
    translateText: function(text){
      this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=${YANDEX_API_KEY}&lang=ru&text=${text}`)
      .then((res) => {
        console.log(res.body.text[0]);
      })
    }
  }
}
</script>

<style>
#app {

}
</style>
