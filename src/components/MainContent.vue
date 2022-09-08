<template>
    <main>
      <div class="container">
        <CreazioneCard :infoAlbum = "arrayFiltrato" /> <!-- Gli passo a infoAlbum (nome della props) l'array filtrato della computed -->
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

    props: {
      cerca: String
    },

    data() {
        return {
            listaDischi: [],
            // cerca: ''
        }
    },
    computed: {
      arrayFiltrato() {
        return this.listaDischi.filter((element) => {
          const genereAlbum = element.genre.toLowerCase()

          if(genereAlbum.includes(this.cerca)) {
            return true
          }
          return false
        })
      }
    },

    mounted() {      
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                this.listaDischi = res.data.response
                console.log(res.data.response)
            })      
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
  