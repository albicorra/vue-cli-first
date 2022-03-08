<template>
  <div id="app">
    <MyTitle/>
    <MyHero/>
  </div>
</template>

<script>
import MyTitle from './components/MyTitle.vue'
import MyHero from './components/MyHero.vue'

export default {
  name: 'App',
  components: {
    MyTitle,
    MyHero
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;  
}

img{
  width: 100%;
}

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
