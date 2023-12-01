<template lang="">
    <v-footer
    class="bg-transparent text-center d-flex flex-column my-4 py-2"
  >
    <div >
      <v-btn
        v-for="icon in icons"
        :key="icon"
        class="mx-4 "
        :icon="icon.icono"
        variant="text"
      ></v-btn>
    </div>

    <v-divider></v-divider>

    <div>
      {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
    </div>
  </v-footer>
</template>
<script>
export default {
    data: () => ({
        icons: [
                {
                icono: 'mdi-whatsapp',
                link: '#'
                },
                {
                icono: 'mdi-instagram',
                link: '#'
                },
                {
                icono: 'mdi-facebook',
                link: '#'
                }
            ],
            items: [{
                    icon: 'mdi-apps',
                    title: 'Home',
                    to: '/'
                },
                {
                    icon: 'mdi-chart-bubble',
                    title: 'Contacto',
                    to: '/inspire'
                }
            ],
    }),
}
</script>

<style scoped>

.footerClass{
    height: 20px !important;
}
</style>