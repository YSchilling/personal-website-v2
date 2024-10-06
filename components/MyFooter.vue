<template>
    <footer class="grid grid-cols-3 items-center mx-auto max-w-screen-xl py-6 px-12">
        <div>
            <h1 class="text-2xl font-bold">Yorick Schilling</h1>
            <p class="text-sm">© 2024 Yorick Schilling. All rights reserved.</p>
        </div>
        <div class="flex flex-col items-center justify-self-center">
            <NuxtLink to="/about" class="duration-300 hover:font-extrabold">About</NuxtLink>
            <NuxtLink to="/projects" class="duration-300 hover:font-extrabold">Projects</NuxtLink>
            <NuxtLink to="/contact" class="duration-300 hover:font-extrabold">Contact</NuxtLink>
        </div>
        <div class="justify-self-end flex gap-2">
            <a href="https://www.linkedin.com/in/yschilling/" target="_blank"><img src="/img/linkedin.png" width="32px"
                    height="32px"></a>
            <a href="https://github.com/YSchilling" target="_blank"><img src="/assets/github.png" width="32px"
                    height="32px"></a>
        </div>
    </footer>
</template>