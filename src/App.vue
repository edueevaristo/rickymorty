<script setup>
import {ref} from 'vue';


</script>

<template>
  <nav class="navbar navbar-expand-lg navbar  bg-primary">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">Rick and Morty</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/">Início</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/about">Sobre</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main">
    <router-view></router-view>
  </div>
  
</template>


<style>
  body {
    background-image: url('./assets/wallpaper.jpg') !important;
    background-position: center;
    background-repeat: no-repeat !important;
    background-size: cover !important;
  }
</style>
