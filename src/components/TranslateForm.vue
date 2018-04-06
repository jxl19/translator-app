<template>
  <div class ="row" id="translateForm">
    <div class="col-md-6 col-md-offset-3">
      <form id="transform" class="form-inline well" v-on:submit="formSubmit">
          <!-- binding this to the data at export by using v-model -->
          <input class="form-control" type = "text" v-model="textToTranslate" placeholder="Enter a word">
          <select class="form-control" v-model="language">
            <option value="ru">Russian</option>
            <option value="es">Spanish</option>
            <option value="fr">French</option>
            <option value="zh">Chinese</option>
          </select>
          <input class="btn btn-primary" type ="submit" value="Translate">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "ru";
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
};
</script>

<style>
    #transform{
        border-radius:10px;
        border:1px #ccc solid;
    }
</style>
