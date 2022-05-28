<template>
  <Banner/>
  <div class="main-container">
    <h1>Create Your Burger</h1>
    <BurgerForm/>

  </div>
</template>

<script>
  import Banner from "../components/Banner.vue";
  import BurgerForm from "@/components/BurgerForm.vue";
  // @ is an alias to /src


  export default {
      name: "HomeView",
      components: { Banner, BurgerForm }
  }
</script>
