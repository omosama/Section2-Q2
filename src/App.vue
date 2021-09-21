<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="https://vuejs.org/images/logo.png" /> -->
    <Category />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Category from './components/Category.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    Category,
  },
};
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
