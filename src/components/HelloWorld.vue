<template>
  <div class="w-full h-full">
    <img src="../assets/logo.png" alt="Vue logo" class="w-24 h-24 fixed">
    <h1 class="text-3xl text-green-700 font-extrabold">{{ msg }}</h1>
    <p class="text-vuegreen">Success! Remove these styles, Add your own and bon coding.</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
