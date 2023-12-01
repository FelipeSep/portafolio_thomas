<template>
  <v-app class="my-app" >
    <default-bar />
    <default-view />
    <default-footer />
  </v-app>
</template>

<script setup>
  import DefaultBar from './AppBar.vue'
  import DefaultView from './View.vue'
  import DefaultFooter from './Footer.vue'
</script>

<style scoped>
  .my-app{
      background-image: url('~@../../fondo.jpg');
      background-size: cover;
      background-position: center center;
      background-attachment: fixed;
    }
</style>
