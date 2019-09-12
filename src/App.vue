<template>
  <div id="app">

      <teszt-component></teszt-component>
      <hr>
      <button @click="change">Push To Array</button>
      <simple-modal v-model="isShow" title="Modal Header">
        <template slot="body">
          <h2>My modal</h2>
          <li v-for="item in myArray" v-bind:key="item">
            {{item}}
          </li>
        </template>
        <template slot="footer">
          <button>OK</button>
        </template>
      </simple-modal>
      <button @click="isShow = !isShow">Modal show/hide button</button>

    <HelloWorld/>
    <TesztComponent/>
    <ListItem/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import TesztComponent from './components/TesztComponent.vue';
import ListItem from './components/ListItem.vue';
import SimpleModal from 'simple-modal-vue';

export default {
  name: 'app',
  components: {
    HelloWorld, TesztComponent, ListItem, SimpleModal
  },
  data() {
    return { myArray: [
        "elso11",
        "masodik22",
        "harmadik33",
      ],
      isShow: false }
  },
  methods: {
    change(){
      this.myArray.push("teszt");
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
