<script setup lang="ts">

  import {} from 'vue';

  const props = defineProps({
    title: {
      type: String,
      default: 'This is a title'
    }
  });

</script>

<template>
  <div>
    <v-row
      class="mt-2"
    >
      <v-col
        class="d-flex align-center justify-center"
      >
        <h1>{{ props.title }}</h1>
  
      </v-col>
    </v-row>
  
    <v-divider></v-divider>
  </div>
</template>
