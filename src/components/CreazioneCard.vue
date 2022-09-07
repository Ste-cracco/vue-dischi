<template>
    <div class="container_card">
        <article class="card" v-for = "(disco, i) in infoAlbum" :key="i">
            <img :src="disco.poster" alt="Cover Album">
            <h3 class="titolo"> {{ disco.title }}</h3>
            <h4 class="autore"> {{ disco.author }} </h4>
            <h5 class="anno"> {{ disco.year }} </h5>            
        </article>
    </div>
</template>
  
<script>
  
export default {
    props: {
        infoAlbum: Array // L'array è listaDischi presente nel data() di MainContent
    },       
}
</script>
  
<style lang="scss" scoped>

.container_card {
    padding: 100px 0;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;

    .card {
        color: white;
        text-align: center;
        background-color: #2E3A46;
        margin: 15px;  
        
        .titolo {
            text-transform: uppercase;
            padding: 0 10px;
        }

        .autore {
            padding-top: 20px;
            padding-bottom: 5px;
            color: gray;
        }

        .anno {
            padding-bottom: 20px;
            color: gray;
        }

        img {
            padding: 25px;
        }

    }
}

</style>
  