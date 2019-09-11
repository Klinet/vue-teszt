<template>
  <div class="main">
    <hr>
    <h1>{{ message }}</h1>

  <ul class="combobox__options">
    <li v-for="result in myArray" v-bind:key="result">
      {{result}}
    </li>
  </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    //message: Array
  },
  data: function () {
    return {
      message: "HelloWorld.vue",
      myArray: [
        "elso1",
        "masodik2",
        "harmadik3",
      ]
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
