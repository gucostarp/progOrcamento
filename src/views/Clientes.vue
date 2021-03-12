<template>
  <div class="about">
    <div class="col-lg-12 mb-3" style="text-align: right;">
    </div>
    <div class="col-lg-12 mb-3" style="text-align: right;">
    <button type="button" class="btn btn-success" data-bs-toggle="modal"
            data-bs-target="#myModal">Inserir</button>
  </div>

    <table class="table">
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">Nome</th>
          <th scope="col">CPF/CNPJ</th>
          <th scope="col">Email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="cliente in clientes" :key="cliente.id">
          <td>{{ cliente.id}}</td>
          <td>{{ cliente.nome }}</td>
          <td>{{ cliente.cpfcnpj }}</td>
          <td>{{ cliente.email }}</td>
          <td>
            <select class="form-select-sm" aria-label="Selecione">
              <option>Selecione</option>
              <option>Excluir</option>
              <option>Alterar</option>
            </select>
          </td>
        </tr>
      </tbody>
    </table>
    <Modal titulo="Inserir Cliente">
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Nome</span>
        <input type="text" class="form-control" placeholder="Nome Completo"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Contato</span>
        <input type="text" class="form-control" placeholder="Contato"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Departamento</span>
        <input type="text" class="form-control" placeholder="Departamento"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">CPF/CNPJ</span>
        <input type="text" class="form-control" placeholder="CPF ou CNPJ"
                aria-label="CPF" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon2">Insc. Mun.</span>
        <input type="text" class="form-control" placeholder=""
                aria-label="Email" aria-describedby="basic-addon2">
        <span class="input-group-text" id="basic-addon2">Insc. Est.</span>
        <input type="text" class="form-control" placeholder=""
                aria-label="Email" aria-describedby="basic-addon2">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon2">Email</span>
        <input type="text" class="form-control" placeholder="Email"
                aria-label="Email" aria-describedby="basic-addon2">
        <span class="input-group-text" id="basic-addon2">Telefone</span>
        <input type="text" class="form-control" placeholder="Telefone"
                aria-label="Email" aria-describedby="basic-addon2">
      </div>

      <label for="basic-url" class="form-label"><b>Endereço</b></label>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon3">Rua</span>
        <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3">
        <span class="input-group-text" id="basic-addon3">Nº</span>
        <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text">Bairro</span>
        <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text">Cidade</span>
        <input type="text" class="form-control" placeholder="" aria-label="Username">
        <span class="input-group-text">Estado</span>
        <input type="text" class="form-control" placeholder="" aria-label="Server">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text">CEP</span>
        <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
      </div>

      <div class="input-group">
        <span class="input-group-text">Observação</span>
        <textarea class="form-control" aria-label="With textarea"></textarea>
      </div>
    </Modal>
</div>
</template>

<script>
import Modal from '@/components/Modal.vue';

const axios = require('axios');

export default {
  data() {
    return {
      clientes: [],
    };
  },
  components: {
    Modal,
  },
  methods: {
    inserirProduto() {

    },
  },
  created() {
    axios.get('http://localhost:3000/clientes')
      .then((response) => {
        // handle success
        // console.log(response);
        this.clientes = response.data;
      });
  },
};
</script>

<style>

</style>
