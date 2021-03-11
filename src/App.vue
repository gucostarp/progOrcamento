<template>
  <v-app class="d-flex">
    <Menu/>
        <router-view/>
        <v-main>
        </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import Menu from './components/Menu.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',

  components: {
    Menu,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
