<template>
    <div>
        <h1>My user!</h1>
        <NuxtLink to="/">Home</NuxtLink> <br/>
        <NuxtLink to="/categories">categories</NuxtLink> <br/>
        <NuxtLink to="/favorite">favorite</NuxtLink> <br/>
        <NuxtLink to="/signature">signature</NuxtLink> <br/>
        <NuxtLink to="/films">films</NuxtLink> <br/>
        <NuxtLink to="/user">user</NuxtLink> <br/>
        <h1>users:</h1>
        <div v-for="usuario in usuarios" :key="usuario.id">
            <NuxtLink :to="'/favorite/'+usuario.id">
                <h1>Nome: {{ usuario.nome}}</h1>
                <h1>email: {{ usuario.email}}</h1>
                <img :src="'http://127.0.0.1:8000'+ usuario.foto" alt="">
            </NuxtLink>

        </div>
        
    </div>
</template>

<script setup>
const {data: usuarios} = await useFetch('http://127.0.0.1:8000/usuarios/')  
</script>