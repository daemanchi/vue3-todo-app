<template>
  <div id="app">
    <h1>My TS App</h1>
    <p><input type="text" v-model="inputText" /></p>
    <p>Count: {{ count }}</p>
    <p><button @click="reset()">Reset</button></p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface State {
  inputText: string;
}

export default defineComponent({
  name: 'App',
  data: (): State => {
    return {
      inputText: ''
    }
  },
  computed: {
    count (): number {
      return this.inputText.length
    }
  },
  methods: {
    reset () {
      this.inputText = ''
    }
  },
});
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
