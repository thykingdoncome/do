<template>
  <div id="app">
   
      <Header />
    
    <router-view/>
  </div>
</template>

<script>

import Header from './components/layout/Header'
export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
