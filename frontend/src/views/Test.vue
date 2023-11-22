<template>
  <div>
    <a style="cursor: pointer;" @click="dialog = true">
      <img class="image" :height="400"
        src="https://images.unsplash.com/photo-1610194352361-4c81a6a8967e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1674&q=80"
        draggable="false" />
    </a>
    <v-dialog v-model="dialog" width="100%">
      <div class="btn"> <v-btn icon="mdi-close" @click="dialog = false"></v-btn></div>
      <v-carousel hide-delimiters height="100vh">
        <v-carousel-item v-for="(item, i) in items" :key="i">
          <v-img :src="item.src" height="100%" contain>
          </v-img>
        </v-carousel-item>
      </v-carousel>


    </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      items: [
        {
          src: 'https://images.unsplash.com/photo-1610194352361-4c81a6a8967e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1674&q=80'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
        }
      ]
    }
  },
}
</script>

<style >
.btn {
  position: absolute;
  display: flex;
  flex-direction: row-reverse;
  width: 100%;
  z-index: 2;
  right: 1em;
}
</style>