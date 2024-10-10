<script setup>

//const isEnglish = useState("isEnglish", () => false);
const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <header class="fixed w-full z-30" style="backdrop-filter: blur(2px);">
        <div class="h-16 flex items-center mx-auto max-w-screen-xl px-6 md:px-8 lg:px-12">
            <NuxtLink to="/" class="flex mr-auto text-xl font-semibold">
                <img width="28" src="/favicon.svg" class="mr-2">
                Yorick Schilling
            </NuxtLink>
            <MobileMenu />
            <nav class="hidden md:flex">
                <NuxtLink to="/about" class="mr-4 text-xl duration-300 hover:font-extrabold">About</NuxtLink>
                <NuxtLink to="/projects" class="mr-4 text-xl duration-300 hover:font-extrabold">Projects</NuxtLink>
                <NuxtLink to="/contact" class="text-xl duration-300 hover:font-extrabold">Contact</NuxtLink>
            </nav>
            <div class="text-2xl mx-4 hidden md:block">|</div>
            <!-- TODO implement DE EN switch 
            <div class="flex mr-3">
                <button @click="isEnglish = false" :class="isEnglish ? '' : 'font-extrabold'"
                    class="duration-300 hover:font-extrabold">DE</button>
                <div class="text-xl mx-1">/</div>
                <button @click="isEnglish = true" :class="isEnglish ? 'font-extrabold' : ''"
                    class="duration-300 hover:font-extrabold">EN</button>
            </div>-->
            <div class="hidden md:flex">
                <button @click="isDarkMode = false" :class="isDarkMode ? '' : 'font-extrabold'"
                    class="duration-300 hover:font-extrabold">Light</button>
                <div class="text-xl mx-1">/</div>
                <button @click="isDarkMode = true" :class="isDarkMode ? 'font-extrabold' : ''"
                    class="duration-300 hover:font-extrabold">Dark</button>
            </div>
        </div>
    </header>
</template>