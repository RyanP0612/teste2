<script setup>
    // let imagemDinas = ['https://classic.exame.com/wp-content/uploads/2023/02/neymar-samba-gold.jpg?quality=70&strip=info&w=1024',
    // 'https://avatars.githubusercontent.com/u/89030432?v=4','https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR0fA2dklh3PFLPpqzmfOqBJ4YKRya8DyHEbQ&usqp=CAU'];


    // acessamos o mecanismo de rotas do NUXT
    const route = useRoute();
    const {data: filmeFound} = await useFetch(`http://localhost:8000/filmes/${route.params.id}`,{
      key: 'filmeRequest' 
    });
</script>

<template>
    <div>
      <h1>
        Welcome to the mato {{ filmeFound.nome}}</h1>
        <br>
        <img :src="'http://localhost:8000' + filmeFound.foto" alt="foto filme">
        <p>Descrição: {{ filmeFound.descricao }}</p>
        <br>
    </div>

</template>