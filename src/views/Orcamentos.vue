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
          <th scope="col">Cliente</th>
          <th scope="col">Produto</th>
          <th scope="col">Valor</th>
          <th scope="col">Quantidade de Itens</th>
          <th scope="col">Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="produto in produtos" :key="produto.id">
          <td>{{ produto.id}}</td>
          <td>{{ produto.cliente}}</td>
          <td>{{ produto.produto }}</td>
          <td>{{ produto.valor }}</td>
          <td>{{ produto.itens }}</td>
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

export default {
  data() {
    return {
      produtos: [],
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
    this.produtos = [
      {
        id: 1,
        cliente: 'Cliente A',
        produto: 'Caixa',
        valor: 15000,
        itens: 4,
      },

      {
        id: 2,
        cliente: 'Cliente B',
        produto: 'Estante',
        valor: 5000,
        itens: 2,
      },

    ];
  },
};
</script>

<style scoped>

</style>
