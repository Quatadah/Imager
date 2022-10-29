<script setup>
import { defineProps } from "vue";
const { withColors } = defineProps(["withColors"]);
const copyUrl = (url) => {
    navigator.clipboard.writeText(url);
};
</script>

<template>
    <v-card class="pa-3 ma-3">
        <v-row>
            <v-col cols="6" v-for="n in 200" sm="3" md="2" lg="1">
                <v-hover v-slot="{ isHovering, props }">
                    <v-card
                        :elevation="isHovering ? 12 : 2"
                        :class="{ 'on-hover': isHovering }"
                        v-bind="props"
                        @click="
                            copyUrl(
                                `https://picsum.photos/500/300?image=${
                                    n * 5 + 10
                                }${withColors ? '' : '&grayscale'}`
                            )
                        "
                    >
                        <v-img
                            :src="`https://picsum.photos/500/300?image=${
                                n * 5 + 10
                            }${withColors ? '' : '&grayscale'}`"
                            :lazy-src="`https://picsum.photos/10/6?image=${
                                n * 5 + 10
                            }${withColors ? '' : '&grayscale'}`"
                            aspect-ratio="1"
                            cover
                        >
                            <template v-slot:placeholder>
                                <v-row
                                    class="fill-height ma-0"
                                    align="center"
                                    justify="center"
                                >
                                    <v-progress-circular
                                        indeterminate
                                        color="grey-lighten-5"
                                    >
                                    </v-progress-circular>
                                </v-row>
                            </template>
                        </v-img>
                    </v-card>
                </v-hover>
            </v-col>
        </v-row>
    </v-card>
</template>
