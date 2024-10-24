<script setup lang="ts">

const isDarkMode = useState("isDarkMode", () => false);

const { data } = await useAsyncData('projects', () => queryContent('/projects').findOne())
const { currentEfforts, pastProjects } = data.value!;

</script>

<template>
    <main class="mb-64">
        <MySection class="flex flex-col items-center pt-32">
            <div class="flex flex-col items-center">
                <h1>PROJECTS</h1>
                <MyDivider width="80%" class="mb-6" />
            </div>
            <p class="text-lg md:text-xl text-center">Below is a list of my most important projects, efforts or
                interests.
                Doesn't
                matter
                what you call it. <br> It is the stuff I did, do and love :)</p>
        </MySection>
        <MySection class="mt-48">
            <h2 class="text-2xl font-extrabold mb-1">My current Efforts</h2>
            <div class="mb-4 self-center"
                :style="`background-color: ${isDarkMode ? 'var(--dark-text-color)' : 'var(--text-color)'}; height: 1px`">
            </div>
            <ProjectCard v-for="effort in currentEfforts" :title="effort.title" :description="effort.description"
                :imageURL="effort.imageURL" :duration="effort.duration" :websiteURL="effort.websiteURL" class="mb-8" />
        </MySection>
        <MySection class="mt-32">
            <h2 class="text-2xl font-extrabold mb-1">Programming Projects</h2>
            <div class="mb-4 self-center"
                :style="`background-color: ${isDarkMode ? 'var(--dark-text-color)' : 'var(--text-color)'}; height: 1px`">
            </div>
            <ProjectCard v-for="project in pastProjects" :title="project.title" :description="project.description"
                :imageURL="project.imageURL" :duration="project.duration" :websiteURL="project.websiteURL"
                class="mb-8" />
        </MySection>
    </main>
</template>

<style scoped>
h1 {
    font-size: clamp(32px, 6vw, 48px);
}
</style>