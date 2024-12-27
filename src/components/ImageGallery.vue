<script setup>
import {ref} from 'vue';


//state for Grayscale mode 
const isGrayMode = ref(false);

// Function to toggle grayscale mode
const toggleColorMode = (mode) => {
  isGrayMode.value = mode === 'gray';
};

// Expose the function to the parent component
defineExpose({ toggleColorMode });
</script>
<template>
    <v-card class="mx-5 my-2 pa-3">
   <v-row>
    <v-col
    v-for="n in 200"
    cols="4"
    sm="3"
    md="2"
    lg="1"
    >
    <v-card >
        <v-img
        :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
        :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
        :class="{ 'grayscale': isGrayMode }"
        style="cursor: pointer;"
        aspect-ratio="1"
        cover
       
      >
      <template v-slot:placeholder>
          <v-row
            align="center"
            class="fill-height ma-0"
            justify="center"
          >
            <v-progress-circular
              color="grey-lighten-5"
              indeterminate
            ></v-progress-circular>
          </v-row>
        </template>
    </v-img>
    </v-card>
    </v-col>
   </v-row>
</v-card>
</template>

<style>
.grayscale {
  filter: grayscale(100%);
}
</style>