  <script setup>
      const { data: filmes } = await useFetch('http://127.0.0.1:8000/filmes')    
  </script>
  
  <template>
    <div>
      <h1>My films</h1>
      <NuxtLink to="/">Home</NuxtLink> <br/>
      <NuxtLink to="/categories">categories</NuxtLink> <br/>
      <NuxtLink to="/favorite">favorite</NuxtLink> <br/>
      <NuxtLink to="/signature">signature</NuxtLink> <br/>
      <NuxtLink to="/films">films</NuxtLink> <br/>
      <NuxtLink to="/user">user</NuxtLink> <br/>
      <h1> filmes </h1>      
      <div :id="'id'+index" v-for="(filme, index) in filmes" :key="index">
         <!-- <NuxtLink :to="`/filmes/${filme.id}`"> 
          <img :src="filme.link"> -->
        <!-- </NuxtLink>     -->
        <h2>{{ filme.nome }}</h2>
        <NuxtLink :to="`/films/${filme.id}`"> 
          <img :src="`http://127.0.0.1:8000${filme.banner}`">
        </NuxtLink> 
      </div> 
    </div>
  </template>
  

  