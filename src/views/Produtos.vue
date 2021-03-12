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
          <th scope="col">Referência</th>
          <th scope="col">Produto</th>
          <th scope="col">Descrição</th>
          <th scope="col">Preço</th>
          <th scope="col">Garantia</th>
          <th scope="col">Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="produto in produtos" :key="produto.id">
          <td>{{ produto.id}}</td>
          <td>{{ produto.referencia}}</td>
          <td>{{ produto.nome }}</td>
          <td>{{ produto.descricao }}</td>
          <td>{{ produto.preco }}</td>
          <td>{{ produto.garantia }}</td>
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
    <Modal titulo="Inserir Produto">
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Referência</span>
        <input type="text" class="form-control" placeholder="Código de Referência"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Nome</span>
        <input type="text" class="form-control" placeholder="Nome do Produto"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text mb-3">Descrição</span>
        <textarea class="form-control" aria-label="With textarea"></textarea>
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">R$</span>
        <input type="text" class="form-control" placeholder="Digite o Valor do Produto"
                aria-label="CPF" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon2">Garantia</span>
        <input type="text" class="form-control" placeholder="Digite a Garantia"
                aria-label="Email" aria-describedby="basic-addon2">
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
        referencia: 'SLB001',
        nome: 'Bebedouro para Ratos',
        descricao: 'Bebedouro confeccionado em Vidro. Não Acompanha o bico e rolha.',
        preco: 40.00,
        garantia: '1 mes',
      },
      {
        id: 2,
        referencia: 'SLP020',
        nome: 'Caixa de Skinner Ethernet',
        descricao: 'A Caixa de Skinner Ethernet Scienlabor é utilizada em laboratórios de psicologia experimental e seu funcionamento é baseado em estímulos visuais, auditivos e olfativos, que elicidam um comportamento operante, fundamentado em três procedimentos: reforço, punição e extinção.',
        preco: 4800.00,
        garantia: '3 meses',
      },
    ];
  },
};
</script>

<style scoped>

</style>
