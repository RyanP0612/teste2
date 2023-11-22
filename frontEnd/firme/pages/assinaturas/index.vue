<script setup>

 const {data: signatures} = await useFetch(`http://localhost:8000/assinatura`,{
      key: 'signRequest' 
    });
</script>

<template>
    <div>
      <h1>Bem vindo as nossas assinaturas!!!</h1>
      <section v-for="sign in signatures" :key="sign.id">
        <h3>Plano => {{  sign.nome }}</h3>

        <p>preço: {{  sign.valor }}</p>
        <hr>
      </section>
    </div>
</template>