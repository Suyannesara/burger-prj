<template>
  <div>
    <NavBar :logo="logo_src" :alt="app_name" />
    <router-view/>
    <Footer/>
  </div>
</template>

<script>
  import NavBar from "./components/NavBar.vue";
  import Footer from "./components/Footer.vue";

  export default {
    name: 'App',
    components: {
      NavBar,
      Footer
    },
    data(){
      return {
        logo_src: 'img/logo.png',
        app_name: 'Make your burger'
      }
    }
  }
</script>

<style>
  *{
    margin: 0;
    padding: 0;

    font-family: 'Helvetica', sans-serif;
    box-sizing: border-box;
  }

  .main-container {
    margin: 50px;
    min-height: 250px;
  }

  h1 {
    text-align: center;
    font-size: 42px;
    margin-bottom: 30px;
    color: #222;
  }
</style>
