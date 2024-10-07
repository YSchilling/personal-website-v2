<script setup>

const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <footer class="grid grid-col-1 md:grid-cols-3 justify-items-center mx-auto max-w-screen-xl py-6 px-12">
        <div class="flex flex-col row-start-3 md:row-start-1">
            <h1 class="text-2xl font-bold self-center md:self-start">Yorick Schilling</h1>
            <p class="text-sm">© 2024 Yorick Schilling. All rights reserved.</p>
        </div>
        <div class="mb-8 md:mb-0 flex flex-col items-center justify-self-center row-start-2 md:row-start-1">
            <NuxtLink to="/about" class="duration-300 hover:font-extrabold">About</NuxtLink>
            <NuxtLink to="/projects" class="duration-300 hover:font-extrabold">Projects</NuxtLink>
            <NuxtLink to="/contact" class="duration-300 hover:font-extrabold">Contact</NuxtLink>
        </div>
        <div class="mb-8 md:mb-0 md:justify-self-end self-center flex gap-2">
            <a href="https://www.linkedin.com/in/yschilling/" target="_blank" class="hover:scale-110 duration-300">
                <img src="/img/linkedin.png" width="32px" height="32px">
            </a>
            <a href="https://github.com/YSchilling" target="_blank" class="hover:scale-110 duration-300">
                <img :src="isDarkMode ? '/vector/github-mark-white.svg' : '/vector/github-mark.svg'" width="32px"
                    height="32px">
            </a>
        </div>
    </footer>
</template>