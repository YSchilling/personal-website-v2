<script setup lang="ts">
useHead({ title: null })
</script>

<template>
    <main class="w-full h-screen flex flex-col justify-center items-center">
        <h1 class="text-6xl">404</h1>
        <p class="mt-2 text-xl">The page you are looking for does not exist.</p>
        <NuxtLink to="/"
            class="text-xl mt-8 border-2 border-black px-2 py-1 duration-300 hover:bg-black hover:text-white">Go
            back home</NuxtLink>
    </main>
</template>