<script setup>
import getImage from '../lib/getImage';
import { Icon } from '@iconify/vue';
import { RouterLink } from 'vue-router';

const { movie } = defineProps(["movie"])
const {
    title,
    id,
    overview,
    backdrop_path: background,
    poster_path: poster,
    release_date,
    vote_average: vote,
    original_language: language
} = movie

const description = overview.length <= 60 ? overview : overview.slice(0, 60) + "..."
</script>

<template>
    <RouterLink :to="`/movies/${id}`">
        <div class="w-full h-full flex justify-center items-center">
            <div
                class="relative w-full max-w-md h-min mx-4 border rounded-md overflow-hidden shadow-lg sm:mx-auto sm:max-w-lg md:max-w-xl lg:max-w-2xl xl:max-w-3xl">
                <img :src="getImage(poster)" class="w-full h-full rounded-t-md object-cover" alt="Movie Poster" />
                <div class="p-4 bg-gray-100 rounded-b-md">
                    <h1 class="text-xl font-semibold my-2 text-neutral-800">{{ title }}</h1>
                    <p class="text-neutral-800 text-sm">{{ description }}</p>
                    <div class="flex items-center gap-1 mt-2">
                        <Icon icon="ph:heart-duotone" class="text-red-500" width="20" />
                        <span>{{ vote }}</span>
                    </div>
                    <div
                        class="group-hover:opacity-100 transition-opacity opacity-0 absolute left-1/2 top-[35%] -translate-x-1/2 flex flex-col gap-2 w-full font-semibold text-white">
                        <div class="w-full flex flex-col items-center justify-center">
                            <button>
                                <Icon icon="ic:round-play-arrow" width="40" class="hover:text-yellow-300" />
                            </button>
                        </div>
                    </div>
                    <div class="absolute bottom-2 right-2 bg-yellow-300 p-2 rounded-full">
                        <Icon icon="akar-icons:plus" class="text-white" />
                    </div>
                </div>
            </div>
        </div>
    </RouterLink>
</template>
