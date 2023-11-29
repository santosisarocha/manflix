<template>
    <div>
        <h1>My categories</h1>
        <NuxtLink to="/">Home</NuxtLink> <br/>
        <NuxtLink to="/categories">categories</NuxtLink> <br/>
        <NuxtLink to="/favorite">favorite</NuxtLink> <br/>
        <NuxtLink to="/signature">signature</NuxtLink> <br/>
        <NuxtLink to="/films">films</NuxtLink> <br/>
        <NuxtLink to="/user">user</NuxtLink> <br/>
        <h1> Categorias disponiveis</h1>
        <h1>Nome: {{ categoria[0].nome }}</h1>
        <h1>Nome: {{ categoria[1].nome }}</h1>
        <h1>Nome: {{ categoria[2].nome }}</h1>

    </div>
</template>

<script setup>
    const { data: categoria } = await useFetch('http://127.0.0.1:8000/categoria')    
  </script>