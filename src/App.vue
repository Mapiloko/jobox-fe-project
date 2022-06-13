<template>
  <FormComponent />
</template>

<script>
import FormComponent from "./components/FormComponent.vue";

export default {
  name: "App",
  components: {
    FormComponent,
  },
};
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  background-color: lightgray;
}
</style>
