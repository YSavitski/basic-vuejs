<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-bind:msg="'Welcome ' + name + ' to Your Vue.js App'"/>
    <input type="text" v-on:change="riseCounter($event)" v-on:input="changeName" placeholder="Input new name"/>
    <div v-if="counter > 0">
      <span>{{'Input has changed ' + counter + ' times'}}</span>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data() {
    return {
      name: 'Anton',
      counter: 0
    }
  },
  methods: {
    changeName: function (event) {
      if (event.target.value) {
        this.name = event.target.value
      }
    },
    riseCounter: function (event) {
      this.counter++;

      if (this.counter && this.counter%2 === 0) {
        event.target.style.color = 'red'
      }
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
