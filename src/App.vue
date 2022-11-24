<script setup lang="ts">
  import { useTheme } from 'vuetify'
  import { computed, ref, watch } from 'vue'
  
  import logo from '@/assets/img/BarUni.webp'

  const theme = useTheme();

  const drawer = ref(false);
  const group = ref(null);

  const pages = ref([
    {
      name: 'Home',
      to: '/'
    },
    {
      name: 'About',
      to: '/about'
    }
  ])

  watch(group, () => {
    drawer.value = false;
  });

  const toggleTheme = function () {
    theme.global.name.value = theme.global.current.value.dark ? 'lightTheme' : 'darkTheme';
  }

</script>

<template>
  <v-app>
    <v-app-bar app color="primary">
      <template v-slot:prepend>
        <v-app-bar-nav-icon variant="image" @click.stop="drawer = !drawer" class="hidden-md-and-up">
        </v-app-bar-nav-icon>
      </template>
      
      <v-app-bar-title>
        <div>
          <v-img
            :src="logo"
            width="100px"
            height="50px"
          />
        </div>
      </v-app-bar-title>
      
      <v-spacer></v-spacer>

      <div class="hidden-sm-and-down">
        <v-btn
          v-for="page in pages"
          :key="`p_${page.name}`"
          :to="page.to"
        >
          {{ page.name }}
        </v-btn>
      </div>

      <v-btn
        @click="toggleTheme"
      >
        <v-icon v-if="theme.global.current.value.dark">mdi-weather-sunny</v-icon>
        <v-icon v-else>mdi-weather-night</v-icon>
      </v-btn>
        
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      bottom
      temporary
      class="hidden-md-adn-up"
    >
      <v-list>
        <v-list-item
          v-for="page in pages"
          :key="page.name"
          :to="page.to"
        >
          {{ page.name }}
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    <v-main>
      <v-container class="fill-height" fluid>
        <router-view v-slot="{ Component }">

          <transition name="fade" mode="out-in">
            <component :is="Component" />
          </transition>

        </router-view>
      </v-container>
    </v-main>
  </v-app>

  <!-- Made: by Joey De Smet With Vue3 / Vuetify -->
  <!-- Github: https://github.com/JoeyDeSmet -->
</template>

<style scoped>
  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s ease-out;
  }
</style>
