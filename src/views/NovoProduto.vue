<template>
  <div>
    <NavbarVue />
    <h1>Criar novo produto</h1>
    <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-text-field v-model="produto.nome" label="Nome do produto" required />
        </v-col>
        <v-col cols="12" md="6">
          <v-text-field v-model="produto.valor" type="number" label="Valor do produto" required />
        </v-col>
      </v-row>
    </v-container>
    <v-btn color="green" @click="cadastrarProduto">Cadastrar</v-btn>
    <v-snackbar v-model="snackbar" :timeout="3000" top>
      {{ mensagem }}
      <v-btn color="white" text @click="snackbar = false">Fechar</v-btn>
    </v-snackbar>
  </div>
</template>
<script>
import NavbarVue from '../components/Navbar.vue'

export default {
  components: {
    NavbarVue
  },
  data(){
    return {
      produto: {
        nome: "",
        valor: 0
      },
      snackbar: false,
      mensagem: ''
    }
  },
  methods: {
    cadastrarProduto(){
      if(!this.produto.nome || !this.produto.valor){
        this.snackbar = true
        this.mensagem = 'Por favor, preencha todos os campos!'
      }else{
        // lógica para cadastrar o produto
        this.snackbar = true
        this.mensagem = 'Produto cadastrado com sucesso!'
      }
    }
  }
}
</script>
<style>
  
</style>