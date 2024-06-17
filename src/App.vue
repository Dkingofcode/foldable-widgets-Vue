<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <WidgetsComponent />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import WidgetsComponent from './components/WidgetComponent.vue';

export default {
  name: 'App',
  components: {
   // HelloWorld
   WidgetsComponent,
  },
  data() {
     return {
       title: 'foldable-widgets-app',
     };
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
