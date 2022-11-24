<script setup lang="ts">

  import { ref } from 'vue';

  const props = defineProps({
    name: {
      type: String
    },
    image: {
      type: String
    },
    description: {
      type: String
    }
  })

</script>

<template>
  <v-card
    height="375px"
  >
    <v-img
      cover
      gradient="to bottom, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.5) 90%"
      class="d-flex align-end justify-end fill-height"
      :src="props.image"
      width="250px"
    >
    <div class="ma-5">
        <span
          style="color: white;"
        >
          {{ props.description }}
        </span>
        <h2 id="name">{{ props.name }}</h2>
      </div>
    </v-img>
  </v-card>
</template>

<style scoped>
  #name {
    color: white;
    font: normal normal normal 28px/1.41em futura-lt-w01-book,futura-lt-w05-book,sans-serif;
  }
</style>
