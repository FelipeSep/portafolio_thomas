<template>
   <v-app-bar
        color="#BA68C8"
        prominent
      >
        <v-toolbar-title>TuKi</v-toolbar-title>
        <router-link to="/">
          <v-btn variant="icon" icon="mdi-home" class="btnStyle"></v-btn>
        </router-link>

        <router-link to="/proyectos">
          <v-btn variant="icon" icon="mdi-image-album" class="btnStyle"></v-btn>
        </router-link>

      </v-app-bar>
</template>

<script setup>
  //
  
</script>

<style>
  .btnStyle{
    color: white;
  }
</style>