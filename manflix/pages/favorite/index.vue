<template>
    <div>
        <h1>My favorite</h1>
        <NuxtLink to="/">Home</NuxtLink> <br/>
        <NuxtLink to="/categories">categories</NuxtLink> <br/>
        <NuxtLink to="/favorite">favorite</NuxtLink> <br/>
        <NuxtLink to="/signature">signature</NuxtLink> <br/>
        <NuxtLink to="/films">films</NuxtLink> <br/>
        <NuxtLink to="/user">user</NuxtLink> <br/>
        <h1> filmes favoritos</h1>
        <h1>Nome: {{ favoritos[0].idFilmeFK.nome}}</h1>
   

    </div>
</template>
<script setup>
const { data: favoritos } = await useFetch('http://127.0.0.1:8000/favoritos')    
</script>