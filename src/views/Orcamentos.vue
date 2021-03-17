<template>
  <div class="about">
    <div class="col-lg-12 mb-3" style="text-align: left;">
    </div>
    <div class="col-lg-12 mb-3" style="text-align: left;">
    <h4>Cadastro de Orçamentos</h4>
    </div>
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
          <th scope="col">Cliente</th>
          <th scope="col">Produto</th>
          <th scope="col">Valor</th>
          <th scope="col">Quantidade de Itens</th>
          <th scope="col">Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="orcamento in orcamentos" :key="orcamento.id">
          <td>{{ orcamento.id}}</td>
          <td>{{ orcamento.cliente}}</td>
          <td>{{ orcamento.produto }}</td>
          <td>{{ orcamento.valor }}</td>
          <td>{{ orcamento.itens }}</td>
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
    <Modal titulo="Inserir Orçamento">
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Selecione o Cliente</span>
        <input type="text" class="form-control" placeholder="Digite o CPF/CNPJ"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Referência</span>
        <input type="text" class="form-control" placeholder="Código de Referência do Produto"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Quantidade</span>
        <input type="text" class="form-control" placeholder="Digite a Quantidade"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Desconto</span>
        <input type="text" class="form-control" placeholder="Digite o Valor do Produto"
                aria-label="CPF" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text mb-3">Observações</span>
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
      orcamentos: [],
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
    axios.get('http://localhost:3000/orcamentos')
      .then((response) => {
        // handle success

        this.orcamentos = response.data;
      });
  },
};
</script>

<style scoped>

</style>
