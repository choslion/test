<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloDefaluts msg="Welcome to Your Vue.js App" />
    <countUpHi />
    <obHi />
  </div>
</template>

<script>
import HelloDefaluts from './components/HelloWorld.vue';
import countUpHi from './components/countUp.vue';
import obHi from './components/objectFor.vue';

export default {
  name: 'App',
  components: {
    HelloDefaluts,
    countUpHi,
    obHi,
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
