<template>
  <Navbar />
  <router-view/>
  <Footer />
</template>

<script>
  import Navbar from './components/nav.vue';
  import Footer from './components/footer.vue';

  export default {
    components:{
      Navbar,
      Footer
    }
  }
</script>

<style>
  *{
      margin: 0 auto;
      padding: 0 auto;
      box-sizing: border-box;
      font-family: Verdana, Geneva, Tahoma, sans-serif;
    }
    #img-client{
      max-width: 80px;
      max-height: 65px;
      margin: 0 auto;
      display: flex;
    }

    .container{
      margin: 1% auto;
      min-height: 400px;
    }

    h1{
      text-align: center;
      font-size: 18px;
      margin-bottom: 1%;
    }



</style>
