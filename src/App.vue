
<script setup>
import {ref} from 'vue';
import SideBar from '@/components/SideBar';
import ImageGallery from '@/components/ImageGallery'

// Reference to the ImageGallery component
const imageGallery = ref(null);

// Handle color mode change from SideBar
const handleColorModeChange = (mode) => {
  imageGallery.value.toggleColorMode(mode);
};
</script>


<template>
  <v-app>
    <!--sidebar-->
  <SideBar @change-color-mode="handleColorModeChange" />
    <v-main>
      <ImageGallery ref="imageGallery" />
    </v-main>
  </v-app>
</template>
