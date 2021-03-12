<template>

  <div id="app" class="container-fluid">
    <div class="container-fluid mb-4" style="text-align: left;">
    </div>
    <div class="container-fluid" style="text-align: left;">
      <img src="./assets/logo.png" width= "20%" alt="">
    </div>
    <div class="container-fluid">
      <Header/>
    </div>
    <div class="container-fluid">
      <router-view/>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
