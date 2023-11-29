<script setup>
    const route = useRoute();
    console.log("route", route);
    const { data: filmes } = await useFetch(`http://127.0.0.1:8000/filmes/${route.params.id}`) 
</script>
<template>
    
    <h2>{{ filmes.nome }}</h2>
    <h2>{{ filmes.descricao }}</h2>
    <h2>{{ filmes.idCategoriaFK.nome }}</h2>
    <img :src="'http://127.0.0.1:8000'+filmes.banner" alt="">

</template>