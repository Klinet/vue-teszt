<template>
  <div class="main">
      <hr>
      <button v-on:click="onClick()">teszt</button>
      <h1>{{ msg }}</h1>
      <p>{{response}}</p>
      <ul class="combobox__options">
        <li v-for="result in myArray" v-bind:key="result">
          {{result}}
        </li>
          <hr>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'TesztComponent',
  props: {

  },
  data: function () {
    return {
      response: '',
      msg: "TesztComponent.vue",
      myArray: [
              "elso11",
              "masodik22",
              "harmadik33",
      ]
    }
  },
  methods: {
    onClick: function () {
    this.response = 'This is an local click event response!'
    }
  }
}
</script>

<style scoped></style>
