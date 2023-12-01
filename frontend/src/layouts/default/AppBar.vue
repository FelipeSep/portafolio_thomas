<template>

   <v-app-bar
   :style="{ 'background-color': backgroundColor, 'transition': 'background-color 0.5s' }"
     flat
      >
      <v-toolbar-title></v-toolbar-title>
      <!--
         <v-toolbar-title></v-toolbar-title>
        
          <router-link to="/">
            <v-btn variant="icon" icon="mdi-home" class="btnStyle"></v-btn>
          </router-link>

          <router-link to="/about">
            <v-btn variant="icon" icon="mdi-account" class="btnStyle"></v-btn>
          </router-link>

          <router-link to="/proyectos">
            <v-btn variant="icon" icon="mdi-view-dashboard" class="btnStyle"></v-btn>
          </router-link>

           <router-link to="#">
            <v-btn variant="icon" icon="mdi-email-plus" class="btnStyle"></v-btn>
          </router-link>  
          
          <v-spacer></v-spacer>
      -->

      <v-tabs
      v-model="tab"
      stacked
    >
      <v-tab value="tab-1" href="/">
        <v-icon>mdi-home</v-icon>
        <span v-if="tab === 'tab-1'">Home</span>
      </v-tab>

      <v-tab value="tab-2" href="/about">
        <v-icon>mdi-account</v-icon>
        <span v-if="tab === 'tab-2'">Sobre mi</span>
      </v-tab>

      <v-tab value="tab-3"  href="/proyectos">
        <v-icon>mdi-view-dashboard</v-icon>
        <span v-if="tab === 'tab-3'">Proyectos</span>
      </v-tab>
    </v-tabs>
    <v-spacer></v-spacer>
      </v-app-bar>
</template>

<script>
  export default {
    data () {
      return {
        tab: null
      }
    },
  }
</script>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const backgroundColor = ref('transparent');

// Función para manejar el evento de desplazamiento
const handleScroll = () => {
  const scrollPosition = window.scrollY;
  // Cambiar el color de fondo del app bar basado en la posición de desplazamiento
  backgroundColor.value = scrollPosition > 50 ? 'rgba(194,190,225, 0.8)' : 'transparent';
};

onMounted(() => {
  // Agregar el evento de desplazamiento cuando el componente está montado
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  // Limpiar el evento de desplazamiento cuando el componente se desmonta
  window.removeEventListener('scroll', handleScroll);
});
  
</script>

<style>
  .btnStyle{
    color: black;
  }
</style>