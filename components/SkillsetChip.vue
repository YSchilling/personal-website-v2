<script setup lang="ts">
const props = defineProps({
    title: String,
    iconURL: String,
    skillType: String
});

const backgroundColor = computed(() => props.skillType == "CS" ? 'rgba(36, 200, 219, 0.1)' : 'rgba(255, 193, 49, 0.1)');
const borderColor = computed(() => props.skillType == "CS" ? 'var(--cs-highlight-color)' : 'var(--es-highlight-color)');

</script>

<template>
    <div class="px-4 py-1 rounded-md flex items-center"
        :style="`background-color: ${backgroundColor}; transition: background-color 300ms; border: solid 1px ${borderColor}`">
        <img v-if="props.iconURL" :src="iconURL" alt="icon" class="mr-2" style="height: 1.3em">
        <div>{{ title }}</div>
    </div>
</template>