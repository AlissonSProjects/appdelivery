<template>
  <div>
    <NavbarVue />
    <h1>Criar novo pedido</h1>
    <v-form @submit.prevent="dialog = true">
      <v-container>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field v-model="pedido.cliente.nome" label="Nome do cliente" required />
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field v-model="pedido.cliente.telefone" type="number" label="Telefone do cliente" required />
          </v-col>
          <v-col cols="12">
            <v-text-field v-model="pedido.cliente.endereco.logradouro" label="Logradouro" required />
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field v-model="pedido.cliente.endereco.numero" type="number" label="Número" @input="onlyNumbers" required />
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field v-model="pedido.cliente.endereco.bairro" label="Bairro" required />
          </v-col>
          <v-col cols="12">
            <v-text-field v-model="pedido.cliente.endereco.complemento" label="Complemento" />
          </v-col>
          <v-col cols="12">
            <v-text-field v-model="pedido.cliente.endereco.referencia" label="Referência" />
          </v-col>
        </v-row>
      </v-container>
    </v-form>
    <v-dialog v-model="dialog" max-width="500">
      <v-card>
        <v-card-title>Confirmação</v-card-title>
        <v-card-text>Tem certeza que deseja criar o pedido?</v-card-text>
        <v-card-actions>
          <v-btn color="green" @click="criarPedido">Sim</v-btn>
          <v-btn color="red" text @click="dialog = false">Não</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-btn color="green" @click="dialog = true">Criar</v-btn>
    <v-snackbar v-model="snackbar" :timeout="3000" top>
      Pedido criado com sucesso!
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
      pedido: {
        cliente: {
          nome: "",
          telefone: "",
          endereco: {
            logradouro: "",
            numero: "",
            bairro: "",
            complemento: "",
            referencia: ""
          }
        },
        listaProdutos: [],
        valorTotal: 0,
        formaPagamento: ""
      },
      dialog: false,
      snackbar: false
    }
  },
  methods: {
    onlyNumbers(event) {
      // permite apenas números no campo de número do endereço
      const { value } = event.target;
      event.target.value = value.replace(/\D/g, '');
    },
    criarPedido(){
      // lógica para criar o pedido
      this.dialog = false;
      this.snackbar = true;
    }
  }
}
</script>

<style>
h1 {
  font-size: 2rem;
  font-weight: bold;
  margin-top: 2rem;
  margin-bottom: 2rem;
}
  
</style>
