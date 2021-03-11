<template>
  <div class="about">
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">Nome</th>
          <th scope="col">CPF</th>
          <th scope="col">Idade</th>
          <th scope="col">Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="cliente in clientes" :key="cliente.id">
          <td>{{ cliente.id}}</td>
          <td>{{ cliente.nome }}</td>
          <td>{{ cliente.cpf }}</td>
          <td>{{ cliente.idade }}</td>
          <td>
            <select class="form-select-sm" aria-label="Selecione">
              <option>Excluir</option>
              <option>Alterar</option>
            </select>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clientes: [],
    };
  },
  created() {
    this.clientes = [
      {
        id: 1,
        nome: 'andré',
        cpf: '12313153',
        idade: 33,
      },
      {
        id: 2,
        nome: 'gustavo',
        cpf: '23424',
        idade: 36,
      },
      {
        id: 3,
        nome: 'bola',
        cpf: '3444',
        idade: 26,
      },
    ];
  },
};
</script>

<style>

</style>
