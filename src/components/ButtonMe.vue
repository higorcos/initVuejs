<template>
  <button @click="mudarCor">Click {{ count }}</button>
</template>

<script>
export default {
    data(){
        return{
            count:0
        }
    },
    // props:{

    // },
    methods:{
        mudarCor: function(){
            this.count = this.count + 1;
            console.log('Chamando',this.count)
        }
    }



}
</script>

<style>

</style>