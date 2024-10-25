<template>
    <main>
        <MySection class="pt-32">
            <ContentDoc class="px-4" />
        </MySection>
    </main>
</template>

<style scoped>
:deep(h1) {
    font-size: clamp(32px, 6vw, 48px);
}

:deep(h2) {
    font-size: clamp(20px, 4vw, 24px);
}

:deep(p) {
    font-size: clamp(16px, 3vw, 18px);
    margin-bottom: 1em;
}
</style>