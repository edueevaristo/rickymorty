<script setup>
    const personagem = defineProps(["name", "url", "image", "status", "species", "gender", "episode", "location"])
    import { ref } from "vue";
    const selectedEpisode = ref(null);
</script>

<template>

    <div class="card mb-3 ms-5 card-personagens card-hover" style="">
        <div class="row g-0">
            <div class="col-md-4">
                <img :src=personagem.image class="img-fluid rounded-start mt-5" alt="Imagem do personagem">
            </div>
            <div class="col-md-8">
                <div class="card-body">
                    <h5 class="card-title">{{ personagem.name }}</h5>
                    Status:
                    <span v-if="personagem.status === 'Alive'" class="badge text-bg-success">{{ personagem.status }}</span>
                    <span v-else-if="personagem.status === 'Dead'" class="badge text-bg-danger">{{ personagem.status }}</span>
                    <span v-else-if="personagem.status === 'unknown'" class="badge text-bg-warning">{{ personagem.status }}</span>
                    <span v-else class="badge text-bg-danger">{{ personagem.status }}</span>
                    
                    <h6 class="card-text"><b>Espécie:</b> {{ personagem.species }} </h6>
                    <h6 class="card-text"><b>Gênero:</b> {{ personagem.gender }}</h6>
                    <p class="card-text"><small class="text-muted"><b>Localização Atual:</b> {{ personagem.location }}</small></p>
                    <span class="badge text-bg-success"><b>Total de episódios:</b> {{ personagem.episode.length }}</span>

                </div>
            </div>
        </div>
    </div>

</template>

<style>

</style>