<template>
    <div>
        <h3>Meu produto: {{ produto.nome }}</h3>
        <h4>Descrição do produto</h4>
        <p>{{ produto.descricao }}</p>
    </div>
  
</template>

<script>
export default {
    data() {
    return {
     
     }
    },
    props: {
        produto: Object,
    },
}
</script>

<style>

</style>