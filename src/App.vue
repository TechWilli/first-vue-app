<template>
  <div id="app">
    <FirstComponent title="My first Vue App" />
  </div>
</template>

<script>
import "./App.css";
import FirstComponent from "./components/FirstComponent";

export default {
  name: "App",
  components: {
    FirstComponent,
  },
};
</script>

<style scoped>
#app {
  text-align: center;
  margin: 0;
  padding: 0;
  background-color: #353b47;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
