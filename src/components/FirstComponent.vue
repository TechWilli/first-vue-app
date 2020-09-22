<template>
    <div class="container animate__animated animate__fadeIn animate__fast">
      <h1 class="title">{{ title }}</h1>
      <!-- <div class="text-wrapper">
        <span class="highlight-text">Vue.js is really awesome!</span>
      </div> -->
      <div>
        <!-- <InputText placeholder="type something nice" v-model="inputValue"/> -->
        <input
          class="text-input"
          type="text"
          placeholder="type something nice"
          v-model="inputValue"
        />
      </div>
      <button class="btn-send" v-on:click="displayMessage">SEND</button>
      <button class="btn-delete" v-on:click="hideMessage">DELETE</button>
      <div class="show-text-container">
        <span>{{ displayedValue }}</span>
      </div>
    </div>
</template>

<script>
// import InputText from "./InputText";

export default {
  name: "FirstComponent",
  components: {
    // InputText
  },
  data() {
    // console.log("props:", this.$props);
    return {
      showMessage: false,
      textButton: "SHOW",
      inputValue: "",
      displayedValue: "",
    };
  },
  methods: {
    displayMessage: function () {
      this.showMessage = true;
      this.displayedValue = this.inputValue.trim() === "" ? "no value sent" : this.inputValue;
    },
    hideMessage: function () {
      this.showMessage = false;
      this.inputValue = "";
    }
  },
  props: {
    title: String,
  },
};
</script>

<style scoped>
.container {
  background-color: rgb(255, 255, 255, 0.1);
  margin: 25px 15px 0 15px;
  padding: 3rem;
  border-radius: 0.4rem;
  border: 2px solid #4abf8a;
}

.show-text-container {
  background-color: rgb(255, 255, 255, 0.1);
  margin-top: 25px;
  padding: 3rem;
  border-radius: 0.4rem;
  border: 2px solid #4abf8a;
  height: 126px;
}

.highlight-text {
  color: #4abf8a;
  font-size: 1.5rem;
}

.text-wrapper {
  margin-top: 2rem;
}

.title {
  font-size: 3.5rem;
  color: white;
}

span {
  font-size: 1.5rem;
  color: white;
}

.btn-send {
  width: 180px;
  background-color: #4abf8a;
  padding: 1rem 2rem;
  border-radius: 0.4rem;
  font-weight: bold;
  font-size: 1.2rem;
  color: white;
  margin-right: 30px;
}
.btn-send:hover {
  background-color: #368863;
  cursor: pointer;
}
.btn-send:focus {
  background-color: #368863;
}

.btn-delete {
  width: 180px;
  background-color: #b94848;
  padding: 1rem 2rem;
  border-radius: 0.4rem;
  font-weight: bold;
  font-size: 1.2rem;
  color: white;
  margin-left: 30px;
}
.btn-delete:hover {
  background-color: #883636;
  cursor: pointer;
}
.btn-delete:focus {
  background-color: #883636;
}

.text-input {
  width: 100%;
  padding: 0.7rem;
  font-size: 1.2rem;
  margin: 1rem 0;
  border-bottom: 2px solid #4abf8a;
  color: white;
}
</style>
