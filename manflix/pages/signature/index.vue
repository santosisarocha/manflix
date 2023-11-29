
<template>
    <div>
        <NuxtLink to="/">Home</NuxtLink> <br/>
        <NuxtLink to="/categories">categories</NuxtLink> <br/>
        <NuxtLink to="/favorite">favorite</NuxtLink> <br/>
        <NuxtLink to="/signature">signature</NuxtLink> <br/>
        <NuxtLink to="/films">films</NuxtLink> <br/>
        <NuxtLink to="/user">user</NuxtLink> <br/>
      <h1>Assinaturas Disponíveis</h1>
      <h1>Nome: {{ assinatura[0].nome }} : preço {{ assinatura[0].valor }}</h1>
      <h1>Nome: {{ assinatura[1].nome }} : preço {{ assinatura[1].valor }}</h1>
      <h1>Nome: {{ assinatura[2].nome }} : preço {{ assinatura[2].valor }}</h1>
    </div>
  </template>
  
  <script setup>
    const { data: assinatura } = await useFetch('http://127.0.0.1:8000/assinatura')    
  </script>
  