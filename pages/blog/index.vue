<script setup lang="ts">
const { data: posts } = await useAsyncData("posts", () => queryContent("/blog").find())

useHead({ title: null })

</script>

<template>
    <main>
        <MySection class="pt-32 flex flex-col items-center">
            <div class="flex flex-col items-center">
                <h1>BLOG</h1>
                <MyDivider width="80%" class="mb-6" />
            </div>
            <p class="text-lg md:text-xl text-center">Sometimes I like to share something. You can find it here.</p>
        </MySection>
        <MySection class="pt-16 flex flex-col items-center">
            <h2 class="text-2xl font-extrabold">Posts</h2>
            <ul class="mt-4">
                <li v-for="post in posts" :key="post._id">
                    <NuxtLink :to="post._path" class="duration-300 hover:font-extrabold">{{ post.title }}</NuxtLink>
                </li>
            </ul>
        </MySection>
    </main>
</template>

<style scoped>
h1 {
    font-size: clamp(32px, 6vw, 48px);
}
</style>