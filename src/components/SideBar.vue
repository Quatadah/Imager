<script setup>
import { defineEmits } from "vue";

const emits = defineEmits(["select-option"]);

const selectOption = (isColored) => {
    emits("select-option", isColored);
};
</script>

<template>
    <v-navigation-drawer expand-on-hover rail permanent>
        <v-list>
            <v-list-item
                prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
                title="Quatadah Nasdami"
                subtitle="quatadah.nasdami@gmail.com"
            >
            </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list density="compact" class="pt-5" nav>
            <v-list-item
                prepend-icon="mdi-image"
                title="Images"
                value="images"
                @click="selectOption(true)"
            />
            <v-list-item
                prepend-icon="mdi-dialpad"
                title="Grayspace Gallery"
                value="grayscaleGallery"
                @click="selectOption(false)"
            />
        </v-list>
    </v-navigation-drawer>
</template>
