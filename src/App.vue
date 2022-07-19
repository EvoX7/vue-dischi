<template>
  <div id="app">
    <Header/>
    <ShowCase/>
    <Footer/>
  </div>
</template>

<script>


import Header from './components/Header.vue';
import ShowCase from './components/ShowCase.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    ShowCase,
    Footer,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background-color: #1a1b4b;
  
}
</style>
