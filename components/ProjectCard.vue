<script setup>

const props = defineProps({
    title: String,
    description: String,
    imageURL: String,
    duration: Stringr,
    websiteURL: String,
});

const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <div id="container" class="p-4 sm:p-6 md:p-8 grid rounded-3xl"
        :style="`background-color: ${isDarkMode ? 'var(--dark-accent-color)' : 'var(--accent-color)'}`">
        <img :src="imageURL" width="200px" height="200px"
            class="project-image row-span-1 lg:row-span-3 mr-2 lg:mr-6 rounded-md lg:rounded-2xl self-center" />
        <h3 class="font-semibold sm:font-medium md:font-normal col-span-2 lg:col-span-1 self-center">{{ title }}</h3>
        <div class="text-sm row-start-3 lg:row-start-1 col-start-3 justify-self-end self-center">{{
            duration }}</div>
        <p class="py-2 lg:pr-6 my-4 col-span-3 lg:col-span-1">{{ description }}</p>
        <div class="flex col-span-2 lg:col-span-3 justify-self-start lg:justify-self-end duration-300 hover:scale-110">
            <a v-if="websiteURL" :href="websiteURL" target="_blank" class="flex items-center">
                <img :src="isDarkMode ? '/vector/web_icon_dark.svg' : '/vector/web_icon.svg'" class="mr-1"
                    style="height: 1em" />
                Visit Website
            </a>
        </div>
    </div>
</template>

<style scoped>
#container {
    grid-template-columns: max-content 1fr max-content;
    grid-template-rows: max-content 1fr max-content;
}

.project-image {
    font-size: clamp(24px, 4vw, 30px);
    width: 1.5em;
}

h3 {
    font-size: clamp(18px, 4vw, 30px);
}

@media screen and (min-width: 1024px) {
    .project-image {
        width: 200px;
        aspect-ratio: 1 / 1;
    }
}
</style>