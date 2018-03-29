<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered By Vue.js</h5>
    <!-- onsubmit runs translate text method made below -->
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data:function(){
    return{
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text){
      this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=${YANDEX_API_KEY}&lang=ru&text=${text}`)
      .then((res) => {
        this.translatedText = res.body.text[0];
      })
    }
  }
}
</script>

<style>
#app {

}
</style>
