<script setup>

//props - onMounted (identificar que a pagina foi montada), reactive, ref (para trabalhar com a referencia dos elementos) 

import {onMounted, reactive, ref} from "vue";
import PersonagensRickyMorty from "../components/listPersonagensRickyMorty.vue";

let personagens = reactive(ref())

//conexao via api (fetch) ou lib axios

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results

  })
})

</script>



<template>
  <main>
    <div class="container-fluid">
      <div class="col-lg-12 mt-4">

          <div class="card-body row">
              <PersonagensRickyMorty
              v-for="personagem in personagens"
              :key="personagem.name"
              :name="personagem.name"
              :url="personagem.url"
              :image="personagem.image"
              :status="personagem.status"
              :species="personagem.species"
              :gender="personagem.gender"
              :episode="personagem.episode"
              :location="personagem.location.name"
            />
          </div>
          
      </div>
    </div>
  </main>
</template>
