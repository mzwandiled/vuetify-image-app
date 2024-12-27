<script setup>
// Import defineEmits from Vue
import { defineEmits } from 'vue';

// Define the emit function
const emit = defineEmits(['change-color-mode']);

// Function to emit the color mode
const emitColorMode = (mode) => {
  emit('change-color-mode', mode);
};
</script>
<template>
     <v-navigation-drawer
     expand-on-hover
     rail
     >
     <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            subtitle="mzwandiledladla@gmail.com"
            title="Mzwandile Dladla"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-image" title="Color Gallery" value="color" @click="emitColorMode('color')"></v-list-item>
          <v-list-item prepend-icon="mdi-dialpad" title="Gray Gallery" value="gray" @click="emitColorMode('gray')"></v-list-item>
        </v-list>
     </v-navigation-drawer>
</template>