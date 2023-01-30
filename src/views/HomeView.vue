<template>
  <div class="container">
    <img src="../../public/img/client.png" alt="Cadastro de Clientes" id="img-client">
    <h1>Cadastro Cliente</h1>
    <formClient />
</div>

</template>

<script>
  import formClient from '../components/formClient.vue';

  export default {
    components: {
      formClient
    }
  }

</script>

<style>
</style>