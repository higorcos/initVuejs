<template>
  <div>

    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Clientes e Produtos</h1>
    <h2>Formulário de Clientes</h2>
    <br>
    <input type="txt" name="nameCliente" id="nameCliente" placeholder="Nome" v-model="nameField"/><br>
    <input type="email" name="emailCliente" id="emailCliente" placeholder="Email" v-model="emailField"/><br>
    <input type="number" name="idadeCliente" id="idadeCliente" placeholder="Idade" v-model="idadeField"/><br>
    <button @click="submitClient">Adicionar</button>
      
    <hr>
    
    <div v-for="(cliente,index) in orderByName" :key="index">
      <ClienteCrud @deleteCliente="deleteCliente" :cliente="cliente"/>
    </div>
    <ProdutoCrud :produto="produto0"/>
    <ButtonMe></ButtonMe>
  </div>
</template>

<script>

import ClienteCrud from './components/ClienteCrud.vue';
import ProdutoCrud from './components/ProdutoCrud.vue';
import ButtonMe from './components/ButtonMe.vue';

import _ from 'lodash';

export default {
  name: 'App',
  components:{
    ClienteCrud,
    ProdutoCrud,
    ButtonMe
  },  

  data(){
    return{
      
      nameField: "AA",
      emailField: "higot@gmail.com",
      idadeField: 1,
      clientes:[
        {
          id:33323,
        nome:'Hugo',
        email:'hugo@gmail.com',
        idade: 22,
      },
      {
        id: 3939,
        nome:'aigor',
        email:'igor@gmail.com',
        idade: 12,
      },
      ],
      produto0:{
        nome:'PC',
        descricao:'Intel i7'
      }
    }
  },
  methods:{
    submitClient: function(){

          const newCliente = {
            id: Date.now(), 
            nome: this.nameField,
            email: this.emailField,
            idade: this.idadeField,
          } 

        this.clientes.push(newCliente);
          console.log(this.clientes)
        // this.nameField = "";
        // this.emailField = "";
        // this.idadeField = 0;
    },
    deleteCliente: function($event){
      // const index = this.clientes.indexOf($event.idCliente);
      const id = $event.idCliente;

      const newClientes = this.clientes.filter(cl=> cl.id != id);
      this.clientes = newClientes;
      
    },
  },
  computed:{
    orderByName(){
      return _.orderBy(this.clientes, ['nome'], ['ASC'])
    },
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
