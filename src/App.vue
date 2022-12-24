<template>
  <img alt="Vue logo" src="./assets/logo.png"><br>
  <button @click="getTodos">Show qoutes</button><br>
  <div v-for="qoute in qoutes" :key="qoute.id">
  {{ qoute }}
  </div>
</template>
<script>

export default {
  name: 'App',
  data() {
    return {
      qoutes: []
    }
  },
  methods: {
    getTodos() {
      fetch('https://api.kanye.rest/')
      .then(response => response.json())
      .then(data => this.qoutes = data)
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
