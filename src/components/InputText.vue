<template>
  <input class="text-input" type="text" :placeholder="placeholder" />
</template>

<script>
export default {
  name: "InputText",
  props: {
    placeholder: String,
  }
};
</script>

<style scoped>
.text-input {
  width: 100%;
  padding: .7rem;
  font-size: 1rem;
  margin: 1rem 0;
  border-bottom: 2px solid #4abf8a;
  color: white;
}
</style>