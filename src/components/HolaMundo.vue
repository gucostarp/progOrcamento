<template>
  <div>
    Hola {{ nombre }} {{ edad }}!! | {{ triploIdade }}!
    <button @click="showMessage">Mostrar</button>
  </div>
</template>

<script>
export default {
  name: 'HolaMundo',
  props: ['nombre', 'edad'],
  computed: {
    triploIdade() {
      return this.edad * 3;
    },
  },
  created() {
    console.log(`foi criado ${this.nombre}`);
  },
  methods: {
    showMessage() {
      window.alert(`teste ${this.nombre}`);
    },
  },
  data: () => ({
    naombre: 'André',
  }),
};
</script>

<style>
  .classezinha{
    background-color: #984849;
  }
</style>
