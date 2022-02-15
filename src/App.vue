<template>

  <div id="app">

    <img alt="Vue logo" src="./assets/logo.png">

    <hello-world
        :msg=text
        @clicked="onClickChild"
    >

    </hello-world>

    <button v-on:click="changeText">test</button>

  </div>

</template>

<script>

import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    'hello-world' : HelloWorld
  },

  created() {
    setInterval(this.changeText, 1000);
  },

  methods: {
    moment(...args) {
      return window.moment(...args);
    },
    changeText() {
      this.text = this.moment().format("MMM DD HH:mm:ss");
    },
    onClickChild (value) {
      console.log(value)
    }
  },
  data() {
    return {
      text: 'marbles'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
