<template>
    <div>
      <Popup/>
      <HelloWorld msg="Welcome to Your Vue.js App" />
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Popup from './components/popup.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Popup
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

@media screen and (max-width: 575px) {
  html{
    height: auto;
  }
          .popup{
            height: 100%;
            top: 0;
        }
    }
</style>
