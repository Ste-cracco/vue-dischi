<template>
    <main>
      <div class="container">
        <CreazioneCard :infoAlbum = "listaDischi" /> <!-- infoAlbum nome della props -->
      </div>
    </main>
  </template>
  
<script>
import axios from "axios"
import CreazioneCard from "./CreazioneCard.vue"
  
  export default {
    components: {
    CreazioneCard
    },

    data() {
        return {
            listaDischi: []
        }
    },

    mounted() {       
        setTimeout(() => {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                this.listaDischi = res.data.response
                console.log(res.data.response)
            })      
        },2000)
    }
  }
</script>
  
<style lang="scss" scoped>

    main {
        background-color: #1E2D3B;
        min-height: 800px;

        .container {
            width: 1200px;
            margin: auto;
        }
    }

</style>
  