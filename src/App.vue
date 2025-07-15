<template>
  <div id="app">
    <FormatTimestap />
  </div>
</template>

<script>
import FormatTimestap from "./components/FormatTimestap.vue";

export default {
  name: "App",
  components: {
    FormatTimestap,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
