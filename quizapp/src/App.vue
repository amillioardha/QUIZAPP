<template>
  <div id="app">
    <img src="./assets/logo (2).png">
    <h1>Di buat oleh Amillio Ardha (6) XII RPL 2</h1>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: justify;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 10%;
  margin-right: 10%;
  padding-left: 5%;
  padding: 5%;
  border-style: solid;
  border-width: 2px;
  border-color: blue;
}
</style>
