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

        <div v-for="favorito in favoritos" :key="favorito.id">
            <h1>nome: {{ favorito.idFilmeFK.nome }}</h1>
            <h1>descricao {{ favorito.idFilmeFK.descricao }}</h1>
            <img :src="'http://127.0.0.1:8000'+favorito.idFilmeFK.banner" alt="">
            
        </div>
        <button @click="setShowForm">add fav</button> 
        <section v-if="showForm === true">
            <div>
                <label for="">Id do filme:</label> <input type="number" v-model="id"> <br>
            </div>
            <button @click="sendForm">Enviar</button>
              

        </section>
        
       
   

    </div>
</template>
<script setup>
    const route = useRoute();
    console.log("route", route);
    const { data: favoritos } = await useFetch(`http://127.0.0.1:8000/favoritos?usuario=${route.params.id}`)    
    let showForm = false;
    const setShowForm = () => {
        showForm = true;
        console.log("showForm", showForm)
        refreshNuxtData() // call nuxt to update dom
    
    } 
    let id;
    const sendForm = async()=> {
        console.log("id", id)
        await useFetch('http://127.0.0.1:8000/favoritos/',{
            method: 'POST',
            body:[{
                "idFilmeFK":id,
                "idUsuarioFK":route.params.id

            },]
            
            
        })
    }
</script>