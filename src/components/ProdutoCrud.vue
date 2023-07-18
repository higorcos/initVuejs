<template>
    <div>
        <h3>Meu produto: {{ nameProduto }}</h3>
        <input type="name" 
        name="nomeProduto"
        v-model="nameProduto" 
        >
        <p>Descrição do produto</p>
        <p>{{ descricao }}</p>
        <input type="txt" 
        name="descricao"
        v-model="descricao" 
        >
        <!-- :value="nameProduto"  == Variável reativa -->
        {{ count }}
    </div>
  
</template>

<script>
export default {
    data() {
    return {
      count: 0,
      nameProduto: 'PC ',
      descricao: 'Descri',
     }
    },
    props: {
        // nome: String,
        // descricao: String,
    },
}
</script>

<style>

</style>