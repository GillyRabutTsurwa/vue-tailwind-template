<template>
  <div class="w-full h-full">
    <img src="../assets/logo.png" alt="Vue logo" class="w-24 h-24 fixed">
    <h1 class="text-red-500 text-3xl">Yo from Tailwing</h1>
    <h2 class="text-vuegreen semibold uppercase">HAH! Tailwing, I meant Tailwind</h2>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
