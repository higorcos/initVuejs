<template>
    <div>
        <h3>Meu produto: {{ nome }}</h3>
        <h4>Descrição do produto</h4>
        <p>{{ descricao }}</p>
    </div>
  
</template>

<script>
export default {
    data() {
    return {
     
     }
    },
    props: {
        nome: String,
        descricao: String,
    
    },
}
</script>

<style>

</style>