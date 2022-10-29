<script setup>
import ImageGallery from "./components/ImageGallery.vue";
import SideBar from "./components/SideBar.vue";
import { ref } from "vue";

const coloredImages = ref(true);

const updateSelection = (isColored) => {
    console.log(isColored);
    coloredImages.value = isColored;
};
</script>

<template>
    <v-app theme="dark">
        <SideBar @select-option="updateSelection" />
        <v-main>
            <ImageGallery :withColors="coloredImages" />
        </v-main>
    </v-app>
</template>
