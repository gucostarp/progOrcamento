<template>
  <div class="about">
    <button type="button" class="btn btn-success" data-bs-toggle="modal"
            data-bs-target="#myModal">Inserir</button>
    <!-- <button type="button" Launch modal</button> -->
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Id</th>
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
          <td>{{ produto.nome }}</td>
          <td>{{ produto.descricao }}</td>
          <td>{{ produto.preco }}</td>
          <td>{{ produto.garantia }}</td>
          <td>
            <select class="form-select-sm" aria-label="Selecione">
              <option>Excluir</option>
              <option>Alterar</option>
            </select>
          </td>
        </tr>
      </tbody>
    </table>
    <Modal titulo="Inserir Produto">
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Nome</span>
        <input type="text" class="form-control" placeholder="Nome Completo"
                aria-label="Nome" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">CPF</span>
        <input type="text" class="form-control" placeholder="CPF"
                aria-label="CPF" aria-describedby="basic-addon1">
      </div>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon2">Email</span>
        <input type="text" class="form-control" placeholder="Email"
                aria-label="Email" aria-describedby="basic-addon2">
      </div>

      <label for="basic-url" class="form-label">Endereço</label>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon3">Rua</span>
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
      // const myModal = new bootstrap.Modal(document.getElementById('myModal'), {});
      // myModal.show();
    },
  },
  created() {
    this.produtos = [
      {
        id: 1,
        nome: 'caixa',
        descricao: 'jsdhajshdjkahk',
        preco: 1200,
        garantia: '3 meses',
      },
      {
        id: 2,
        nome: 'Penis',
        descricao: 'hfjashdjahs',
        preco: 1.5,
        garantia: '1 mes',
      },
    ];
  },
};
</script>

<style scoped>

</style>
