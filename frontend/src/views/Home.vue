<template>
  <v-container>
      <v-row no-gutters justify="center">
          <v-col cols="12" sm="3" md="3">
              <v-card
              class="ma-2 pa-2 text-center texto-negro-con-borde"
              max-width="auto"
              height="400"
              image="https://images.pexels.com/photos/2088170/pexels-photo-2088170.jpeg"
              title="Sobre mi"
              theme="light"
              link
              href="/about"
              ></v-card>
          </v-col>
          <v-col cols="12" sm="3" md="3">
              <v-card
              class="ma-2 pa-2 text-center title-bottom texto-negro-con-borde"
              max-width="auto"
              height="400"
              image="https://images.pexels.com/photos/2911540/pexels-photo-2911540.jpeg"
              title="Proyectos"
              theme="dark"
              link
              href=""
              ></v-card>
          </v-col>
          <v-col cols="12" sm="3" md="3" >
              <v-card
              class="ma-2 pa-2 text-center title-bottom texto-negro-con-borde"
              max-width="auto"
              height="400"
              image="https://images.pexels.com/photos/4210783/pexels-photo-4210783.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              title="Contacto"
              theme="light"
              link
              >
          </v-card>
          </v-col>
      </v-row>
      
  </v-container>
</template>

<script setup>

</script>

<style scoped>
.texto-negro-con-borde {
  color: black; /* Color del texto */
  text-shadow: 1px 1px 0 white, -1px -1px 0 white, 1px -1px 0 white, -1px 1px 0 white; /* Borde blanco alrededor de cada letra */
}
</style>
