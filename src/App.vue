<template>
  <div id="app">
    <NavBar />
    <router-view/>
    <Footer />
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {

  }
}
</script>

<style>

#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}
</style>
