<script setup lang="ts">

const menuActive = ref(false);
const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <!-- Icon -->
    <svg class="ham hamRotate ham8 z-50 block md:hidden -mr-4" :class="menuActive ? 'active' : ''" viewBox="0 0 100 100"
        width="56" @click="menuActive = !menuActive;">
        <path class="line top" :stroke="isDarkMode || menuActive ? 'white' : 'black'"
            d="m 30,33 h 40 c 3.722839,0 7.5,3.126468 7.5,8.578427 0,5.451959 -2.727029,8.421573 -7.5,8.421573 h -20" />
        <path class="line middle" :stroke="isDarkMode || menuActive ? 'white' : 'black'" d="m 30,50 h 40" />
        <path class="line bottom" :stroke="isDarkMode || menuActive ? 'white' : 'black'"
            d="m 70,67 h -40 c 0,0 -7.5,-0.802118 -7.5,-8.365747 0,-7.563629 7.5,-8.634253 7.5,-8.634253 h 20" />
    </svg>

    <!-- Menu -->
    <div class="mmcontainer duration-300 flex flex-col items-center z-40" :class="menuActive ? 'active' : ''">
        <div class="flex items-center self-start text-white h-16">
            <button @click="isDarkMode = false" :class="isDarkMode ? '' : 'font-extrabold'"
                class="duration-300 hover:font-extrabold">Light</button>
            <div class="text-xl mx-1">/</div>
            <button @click="isDarkMode = true" :class="isDarkMode ? 'font-extrabold' : ''"
                class="duration-300 hover:font-extrabold">Dark</button>
        </div>
        <ul class="w-full flex flex-col items-center mt-12 text-white">
            <li @click="menuActive = false" class="text-2xl mb-6">
                <NuxtLink to="/">Home</NuxtLink>
            </li>
            <li @click="menuActive = false" class="text-2xl mb-6">
                <NuxtLink to="/about">About</NuxtLink>
            </li>
            <li @click="menuActive = false" class="text-2xl mb-6">
                <NuxtLink to="/projects">Projects</NuxtLink>
            </li>
            <li @click="menuActive = false" class="text-2xl mb-6">
                <NuxtLink to="/contact">Contact</NuxtLink>
            </li>
            <li @click="menuActive = false" class="text-2xl">
                <NuxtLink to="/blog">Blog</NuxtLink>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.mmcontainer {
    width: 100vw;
    height: 100vh;
    position: fixed;
    left: 0;
    top: -100vh;
    padding: 0 32px 0 32px;
    background-color: rgba(0, 0, 0, 0.8)
}

.mmcontainer.active {
    top: 0;
}

.ham {
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
    transition: transform 400ms;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

.hamRotate.active {
    transform: rotate(45deg);
}

.line {
    fill: none;
    transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
    stroke-width: 5.5;
    stroke-linecap: round;
}

.ham8 .top {
    stroke-dasharray: 40 160;
}

.ham8 .middle {
    stroke-dasharray: 40 142;
    transform-origin: 50%;
    transition: transform 400ms;
}

.ham8 .bottom {
    stroke-dasharray: 40 85;
    transform-origin: 50%;
    transition: transform 400ms, stroke-dashoffset 400ms;
}

.ham8.active .top {
    stroke-dashoffset: -64px;
}

.ham8.active .middle {
    transform: rotate(90deg);
}

.ham8.active .bottom {
    stroke-dashoffset: -64px;
}
</style>