<template>
  <div id="app" class="w-full h-screen p-4">
    <HelloWorld msg="Hello World from Vue & Tailwind" />
    <p class="text-red-500"> Punchi ma pannko</p>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld
  }
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
