<template>
<div>

    <h2>{{ nameUpperCase }} </h2>
    <h4>{{ cliente.email }}</h4>
    <h5 v-show="showIdade"
    :class="{'a':showIdade,'b':!showIdade }"
    >{{ cliente.idade }}</h5>
    <button @click="$emit('deleteCliente',{idCliente:cliente.id})">Deletar</button>
</div>
</template>

<script>
export default {
    

    data(){
        return{
        }
    },
    props:{
        cliente:Object,
        showIdade: Boolean,
    },
    methods:{
       
    },
    computed:{
        nameUpperCase(){   
            return  this.cliente.nome.toUpperCase()
        },
        gerarId(){
            return (this.cliente.nome+this.cliente.email+this.cliente.idade+Date.now()).toUpperCase()
        }
  },
 
}
</script>

<style scoped>

</style>
