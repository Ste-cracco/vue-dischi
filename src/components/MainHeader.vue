<template>
    <header>
        <div class="logo">
            <img src="../assets/logo.png" alt="">
        </div>      
        <div class="container_select">
          <span> Seleziona il genere musicale</span>
          <select v-model="cerca" @change= "$emit('search', cerca)" name="Generi"  >
              <option value="">Tutti</option>
              <option value="rock">Rock</option>
              <option value="pop">Pop</option>
              <option value="jazz">Jazz</option>
              <option value="metal">Metal</option>
          </select>
          
        </div>
    </header>
  </template>
  
  <script>
  
  export default {
      name: "MainHeader",
      data() {
        return {
          cerca: ''
        }
      }
  }
  </script>
  
  <style lang="scss" scoped>
  
    header {
        background-color: #2E3A46;
        height: 60px;
        display: flex;
        align-items: center;

        .logo {
            width: 55px;
            padding: 10px;
        }

        .container_select {
          color: white;

          span {
            padding: 0 10px;
          }
        }
    }
  </style>