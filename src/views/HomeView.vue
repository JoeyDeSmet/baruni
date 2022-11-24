<script setup lang="ts">
  import team from '@/assets/img/Team.webp'
  import product from '@/assets/img/product.jpeg'
  import TitleDivider from '@/components/TitleDivider.vue';

  import { ref } from 'vue';

  const center = ref({lat: 51.093048, lng: 6.842120});
  const markers = ref([
    {
      position: {
        lat: 51.093048, lng: 6.842120
      },
    }
    , // Along list of clusters
  ]);

</script>

<template>
  <div>
    <v-row>
      <v-col 
        cols="12"
      >
        <v-img 
          cover
          :src="team"
          max-height="550px"
          gradient="to bottom, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.5) 90%"
          class="d-flex align-end justify-end"
        >
          <div
            class="ma-5"
          >
            <h1>Welkom</h1>
            <p>Wij zijn Baruni</p>
          </div>
        </v-img>
      </v-col>
    </v-row>

    <TitleDivider title="Our Product"/>

    <v-divider></v-divider>

    <v-row class="ma-10">
      <v-col cols="12" md="8" :offset="$vuetify.display.mdAndUp ? 2 : 0">
        <v-card elevation="5"> 
          <v-row>
            <v-col cols="12" md="6">
              <v-img
                :src="product"
                cover
                class="fill-height"
              ></v-img>
            </v-col>

            <v-col 
              cols="12" 
              md="4"
              class="d-flex flex-column justify-center align-center"
            >
              <div class="ma-5">
                <h3>"Met passie streven naar perfectie"</h3><br/>
                We verkopen met Baruni een luxe product. Het is een chocoladebar met een krokant laagje van feuilletine en knettersuiker met daarop een zachte ganache van melkchocolade met een toets van framboos en merengue. Bovenop de ganache bevindt zich een smeuïge gezouten karamel. Dit alles wordt omhuld met kwalitatieve melkchocolade.
              </div>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <TitleDivider title="Contact"/>

    <v-row class="ma-10">
      <v-col cols="12" md="8" :offset="$vuetify.display.mdAndUp ? 2 : 0">
        <v-card
          elevation="5"
          class="d-flex flex-column align-center justify-center text-center"
          color="accent"
        >
          <div class="ma-5">
            <p>Bakkerij-, Slagerij-, Hotelschool Ter Groene Poorte,<br/> Spoorwegstraat, Brugge, België</p>
            <v-spacer></v-spacer>
          </div>
          
          <div class="ml-5 mr-5">
            <p>Email: <a data-auto-recognition="true" href="mailto:info@baruni.be" style="text-decoration: none;">info@baruni.be</a></p>
            <v-spacer></v-spacer>
          </div>
    
          <div>
            <v-btn icon="mdi-instagram" class="ma-3" href="https://www.instagram.com/baruni.vlajo/"></v-btn>
            <v-btn icon="mdi-facebook" class="ma-3" href="https://www.facebook.com/profile.php?id=100086272700290"></v-btn>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>
