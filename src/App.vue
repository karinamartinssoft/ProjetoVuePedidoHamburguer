<template>
 <NavBar :logo="logo_src" :alt="app_name" />
  <RouterView/>
  <Footer></Footer> 
</template>

<script>
import NavBar from './components/NavBar.vue';
import Footer from './components/Footer.vue';

export default {
  components: {
    NavBar,
    Footer
  },
  data(){
    return {
      logo_src: "/img/logo.png",
      app_name: "Crie seu Hamburguer"
    }
  }
  
}
</script>

<style>
* {
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main-container{
  margin: 50px;
  min-height: 250px;
}

h1{
  text-align: center;
  font-size: 42px;
  color: #222;
}
</style>
