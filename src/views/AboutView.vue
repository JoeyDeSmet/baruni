<script setup lang="ts">
  import { ref } from 'vue'
  import team from '@/assets/img/Team.webp'
  import { useElementSize } from '@vueuse/core'
  import TitleDivider from '@/components/TitleDivider.vue'
  import Person from '@/components/Person.vue'

  import User from '@/assets/img/user.png'

  import Alexandria from '@/assets/img/Alexandria.jpeg'
  import Bram from '@/assets/img/Bram.jpeg'
  import Daan from '@/assets/img/Daan.jpeg'
  import Eliane from '@/assets/img/Eliane.jpeg'
  import Jason from '@/assets/img/Jason.jpeg'
  import Kevin from '@/assets/img/Kevin.jpeg'
  import Lieze from '@/assets/img/Lieze.jpeg'
  import Renske from '@/assets/img/Renske.jpeg'
  import Thomas from '@/assets/img/Thomas.jpeg'
  import Thibault from '@/assets/img/Thibault.jpeg'

  const aboutSheet = ref(null);
  const { width, height } = useElementSize(aboutSheet);

  const persons = ref([
    {
      name: 'Kevin Bakeland',
      image: Kevin,
      description: 'Financieel directeur'
    },
    {
      name: 'Alexandra Bart',
      image: Alexandria,
      description: 'Assistent financieel directeur'
    },
    {
      name: 'Daan Baes',
      image: Daan,
      description: 'Gedelegeerd bestuurder'
    },
    {
      name: 'Eliane Verbruggen',
      image: Eliane,
      description: 'Commercieel directeur'
    },
    {
      name: 'Bram Hardeman',
      image: Bram,
      description: 'Assistent commercieel directeur'
    },
    {
      name: 'Jason De Smet',
      image: Jason,
      description: 'ICT'
    },
    {
      name: 'Lieze Nijsens',
      image: Lieze,
      description: 'Technische directeur'
    },
    {
      name: 'Renske Jans',
      image: Renske,
      description: 'Vlinder'
    },
    {
      name: 'Thomas Vanfleteren',
      image: Thomas,
      description: 'Administratief directeur'
    },
    {
      name: 'Thibault Hessens',
      image: Thibault,
      description: 'Assistent gedelegeerd bestuurder'
    }
  ]);

</script>

<template>
  <div>
    <v-row>
      <v-col cols="10" offset="1">
        <v-card
          ref="aboutSheet"
          elevation="5"
          class="d-flex flex-column text-center justify-center align-center mb-8"
        >
          <div
            class="ma-10"
          >
            <h2>About us</h2>
            <p>Wij zijn Baruni. Een team van gemotiveerde leerlingen die de opleiding chocolade & patisserie volgen.<br/> Wij streven met passie naar perfectie om u een zo goed mogelijke service te kunnen bieden.</p>
          </div>

          <div class="mt-10">
            <v-img
              cover
              :src="team"
              max-height="500px"
              :width="width"
            ></v-img>
          </div>
        </v-card>
      </v-col>
    </v-row>

    <TitleDivider title="Introductions"/>

    <v-row justify="space-around" class="mt-5">
      <Person
        v-for="person in persons"
        :key="`p_${person.name}`"
        :name="person.name"
        :image="person.image"
        :description="person.description"
        class="ma-5"
      />
    </v-row>
  </div>
  <!-- Made: by Joey De Smet With Vue3 / Vuetify -->
  <!-- Github: https://github.com/JoeyDeSmet -->
</template>

<style scoped>

</style>
