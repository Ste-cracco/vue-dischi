<template>
  <div>
    <MainHeader/>
    <MainContent/>
  </div>
    
</template>

<script>
import MainContent from './components/MainContent.vue';
import MainHeader from './components/MainHeader.vue';


export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent,
  }
}
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}

img {
  max-width: 100%;
}
</style>
