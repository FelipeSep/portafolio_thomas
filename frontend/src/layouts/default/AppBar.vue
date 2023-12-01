<template>

   <v-app-bar
   :style="{ 'background-color': backgroundColor, 'transition': 'background-color 0.5s','box-shadow': boxShadow  }"
     flat
      >
      <v-toolbar-title></v-toolbar-title>
      
          <v-btn
            class="ma-2 btnStyle"
            href="/"
          >
            <v-icon
              end
              icon="mdi-home"
              class="mx-1"
            ></v-icon>
            Home
          </v-btn>
          <v-btn
            class="ma-2 btnStyle"
            href="/about"
          >
            <v-icon
              end
              icon="mdi-account"
              class="mx-1"
            ></v-icon>
            About me
          </v-btn>
          <v-btn
            class="ma-2 btnStyle"
            href="/proyectos"
          >
            <v-icon
              end
              icon="mdi-view-dashboard"
              class="mx-1"
            ></v-icon>
            Projects
          </v-btn>
          <v-btn
            class="ma-2 btnStyle"
            href="#"
          >
            <v-icon
              end
              icon="mdi-email-plus"
              class="mx-1"
            ></v-icon>
            Contact
          </v-btn>
          <v-spacer></v-spacer>

        
    </v-app-bar>
</template>



<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const backgroundColor = ref('transparent');
const boxShadow = ref('none'); // Inicialmente sin sombra

// Función para manejar el evento de desplazamiento
const handleScroll = () => {
  const scrollPosition = window.scrollY;
  // Cambiar el color de fondo del app bar basado en la posición de desplazamiento
  backgroundColor.value = scrollPosition > 50 ? 'rgba(194,190,225, 0.85)' : 'transparent';
  boxShadow.value = scrollPosition > 50 ? '0px 2px 10px rgba(0, 0, 0, 0.2)' : 'none';
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
    font-family: 'Pixelify Sans', sans-serif;
    font-size: 19px !important;
  }

</style>