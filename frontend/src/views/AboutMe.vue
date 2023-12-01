<template>

  <v-container class="fontStyle" transparent>
    <v-row no-gutters>
      <v-col>
        <v-row >
            <v-sheet class="ma-2 pa-2 text-center justify-center" style="background-color: transparent !important;">
                <h1>About Me</h1>
                Hi! i'm cal (or c6)
                <hr>
                <h2>Animanga</h2>
                eva, shoujo shuumatsu ryokou, haibane renmei, alien 9, yuyushiki, nichijou. shimeji simulation, ashizuri suizokukan
                u can friend request me on mal here!!!! although my ratings are not really that serious
                <hr>
                <h2>Music</h2>
                sextrance, anything hardcore edm, screamo, anything emo, cloud rap
                u can add me on my rym if ur interested on my fav bands :D
                <hr>
                <h2>Games</h2>
                subarashiki hibi, ultrakill, superhot, post-void, mirror's edge, M.O.A.B.O.M, #21 the world and just vns/trippy games overall.
                u can add my steam here!
                <hr>
                
        </v-sheet>
        </v-row>

        <v-row class="text-center justify-center">
            <v-sheet class="text-center justify-center" style="background-color: transparent !important;">                
                <div>
                    <iframe width="480" height="320" :src="youtubeVideoUrl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
                </div>
        </v-sheet>

        
    </v-row>
    <v-row class="text-center justify-center mt-6" >
                <v-btn 
                    class="text-none"
                    prepend-icon="mdi-arrow-left"
                    color="medium-emphasis"
                    min-width="92"
                    rounded
                    variant="outlined"
                    @click="dialog = false"
                    href="/"
                >
                    Back to home
                </v-btn>        
    </v-row>
 


        
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
    data() {
        return {
            youtubeVideoUrl: "https://www.youtube.com/embed/75zHkAHeOGo?si=srhLIm-HWJ8_A9aC" // Reemplaza esto con la URL de tu video de YouTube
        }
    },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pixelify+Sans&display=swap');

hr{
    margin-top: 1em;
    margin-bottom: 1em;
    border-color: purple;
}

h1,h2{
    font-family: 'Pixelify Sans', sans-serif;
}

iframe {
        max-width: 440 !important;
        max-height: 315 !important;
    }

</style>