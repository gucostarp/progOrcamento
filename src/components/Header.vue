<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light nav-tabs"  >
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNavAltMarkup"
      aria-controls="navbarNavAltMarkup"
      aria-expanded="false"
      aria-label="Alterna navegação"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <router-link class="nav-item nav-link" to="/clientes">Clientes</router-link>
        <router-link class="nav-item nav-link" to="/produtos">Produtos</router-link>
        <router-link class="nav-item nav-link" to="/orcamentos">Orçamentos</router-link>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style>
</style>
