<template>
    <div>
        <div :class= " show === true ? 'preloader' : 'pippo' ">
            <span>Caricamento in corso...</span>
        </div>
    </div>
</template>

<script>  
    export default {
        name: 'LoaderContent', 
    
        data() {
            return {
                show: true
            }
        },
        mounted() {
            this.Toggle()
        },
        methods: {
            Toggle() {
                setTimeout(() => {
                    this.show = false
                }, 2000)
            }
        }
    }
    
</script>

<style lang="scss" scoped>

    .pippo{
        display: none;
    }

    .preloader {
        z-index: 999;
        background-color: red;
        display: block;
    }
    
</style>
  