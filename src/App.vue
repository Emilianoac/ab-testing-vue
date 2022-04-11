<template>
  <h1 v-if="randomNumber == 1"> Version 1 </h1>
  <h1 v-else-if="randomNumber == 2"> Version 2 </h1>
  <h1 v-else-if="randomNumber == 3" > Version 3 </h1>
</template>

<script>

export default {
  name: 'App',
  setup() {
    let randomNumber = Math.floor(Math.random() * 3) + 1

    if (!localStorage.getItem('randomNumber')) {
      localStorage.setItem('randomNumber', randomNumber)
    }

    /* if(localStorage.getItem('randomNumber') != randomNumber) {
      randomNumber = localStorage.getItem('randomNumber')
    } */

    return {
      randomNumber
    }
  }
}
</script>

<style>

body {
  background-color: #071e34;
  color: white;
  padding: 0;
}

h1 {
  border-bottom: 5px solid #09744b;
  max-width: max-content;
  margin: auto;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px
}
</style>
