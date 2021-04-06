<template>
  <div id="app">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>
<style>
html{
  height: 100%;
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(to right top,#65dfc9,#6cdbeb);
}

@media screen and (max-width: 536px) {
  html{
    height: auto;
  }
}
</style>