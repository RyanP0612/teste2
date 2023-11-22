<script setup>
// função useFetch vai chamar o backend como se fosse no Insomnia
    const { data: allFilmes } = await useFetch('http://localhost:8000/filmes',{
      key: 'filmeRequest' 
    });
    
    
    
</script>



<template>
    <div>
        <h1>Bem vindo aos nossos filmes</h1>
        <section v-for="filme in allFilmes" :key="filme.id">
            <h3>{{ filme.nome }}</h3>
            <!-- <img :src="'http://localhost:8000' + filme.foto" alt="foto filme"> -->
            <!-- <NuxtLink :to="'/trips/' + image.tripFk"></NuxtLink> -->

            <NuxtLink :to="`/filmes/${filme.id}`">
                <img :src="'http://localhost:8000' + filme.foto" alt="foto filme">
            </NuxtLink>
        </section>
        <br><hr>
    </div>
</template>

        
