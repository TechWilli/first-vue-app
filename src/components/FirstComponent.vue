<template>
  <div>
    <div class="container animate__animated animate__fadeIn">
      <h1 class="title">{{ title }}</h1>

      <div class="text-wrapper">
        <span class="highlight-text">Vue.js is really awesome!</span>
      </div>

      <button class="btn-click" v-on:click="displayMessage">{{ textButton }}</button>
      <div class="container animate__animated animate__fadeInDown animate__fast" v-if="showMessage">
        <span>XPTO</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FirstComponent",
  data() {
    // console.log("props:", this.$props);
    return {
      showMessage: false,
      textButton: "SHOW",
    };
  },
  methods: {
    displayMessage() {
      this.showMessage = !this.showMessage;
      this.textButton = this.textButton === "SHOW" ? "HIDE" : "SHOW";
      console.log("botão clicado", this.showMessage);
    },
  },
  props: {
    title: String,
  },
};
</script>

<style scoped>
.container {
  background-color: rgb(255, 255, 255, 0.1);
  margin: 2rem;
  padding: 3rem;
  border-radius: 0.4rem;
  border: 2px solid #4abf8a;
}

.highlight-text {
  color: #4abf8a;
  font-size: 1.5rem;
}

.text-wrapper {
  margin: 2rem 0;
}

.title {
  font-size: 3.5rem;
  color: white;
}

span {
  font-size: 1.5rem;
  color: white;
}

.btn-click {
  width: 180px;
  background-color: #4abf8a;
  padding: 1rem 2rem;
  border-radius: 0.4rem;
  font-weight: bold;
  font-size: 1.2rem;
  color: white;
}

.btn-click:hover {
  background-color: #368863;
  cursor: pointer;
}
</style>
