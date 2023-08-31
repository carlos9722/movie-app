<script setup>
import getImage from "../lib/getImage"
import { Icon } from '@iconify/vue';
import { RouterLink } from 'vue-router';
const { banner } = defineProps(["banner"])
const {
    id,
    title,
    overview,
    backdrop_path: background,
} = banner
const description = overview.lenght <= 200 ? overview : overview.slice(0, 200) + '...'
</script>

<template>
    <div class="w-screen h-screen" :style="{
        backgroundImage: 'url(' + getImage(background) + ')',
        backgroundPosition: 'center center',
        backgroundSize: 'cover'
    }">
        <div
            class="text-white p-10 flex flex-col justify-center w-full h-full bg-gradient-to-r from-black to to-trasnparent">
            <h1 class="text-8xl font-bold">{{ title }}</h1>
            <p class="mt-2 w-1/2 text-neutral-400">{{ description }}</p>
            <RouterLink :to="`/movies/${id}`"
                class="flex items-center gap-1 px-6 py-4 rounded-full bg-yellow-400 w-fit mt-4 transition hover:bg-neutral-800 font-semibold">
                <span>Watch Trailer</span>
                <span>
                    <Icon icon="ic:round-play-arrow" />
                </span>
            </RouterLink>
        </div>
    </div>
</template>