<template>
  <div>
    <LoaderContent/>
    <MainHeader @search="onSearch"/>
    <MainContent :cerca="cercaProp"/>
  </div>
    
</template>

<script>
import MainContent from './components/MainContent.vue';
import MainHeader from './components/MainHeader.vue';
import LoaderContent from './components/LoaderContent.vue';


export default {
  name: 'App',
  data() {
    return {
      cercaProp: ''
    }
  },

  components: {
    LoaderContent,
    MainHeader,
    MainContent   
  },

  methods: {
    onSearch(data) {
      this.cercaProp = data
      console.log(data)
    }
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

.active {
  display: block;
}
</style>
