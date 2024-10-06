<script setup>

const props = defineProps({
    title: String,
    description: String,
    imageURL: String,
    duration: Number,
    websiteURL: String,
});

const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <div id="container" class="p-8 grid rounded-3xl"
        :style="`background-color: ${isDarkMode ? 'var(--dark-accent-color)' : 'var(--accent-color)'}`">
        <img :src="imageURL" width="200px" height="200px" class="row-span-3 mr-6 rounded-2xl"
            style="width: 200px; height: 200px" />
        <h3 class="text-3xl">{{ title }}</h3>
        <div class="text-sm">{{ duration }}</div>
        <p class="py-2 pr-6 pl-1">{{ description }}</p>
        <div class="flex col-span-2 justify-self-end duration-300 hover:scale-110">
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
</style>