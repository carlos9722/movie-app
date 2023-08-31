<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <nav
        class="flex text-white items-center gap-20 absolute left-0 right-0 mx-6 py-4 top-4 bg-transparent border-neutral-400">
        <RouterLink to="/" class="gap-2">
            <img src="../assets/logo.png" alt="logo" class="w-20 h-auto">
        </RouterLink>

        <div class="hidden md:flex flex-grow items-center justify-center">
            <ul class="flex gap-4 font-semibold">
                <li class="text-yellow-300">MOVIES</li>
                <li>CELEBS & PHOTOS</li>
                <li>COMMUNITY</li>
                <li>NEWS</li>
            </ul>
        </div>
    </nav>
</template>
