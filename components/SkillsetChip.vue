<script setup lang="ts">
enum SkillType {
    CS = "Computer Science",
    ES = "Entrepreneurship",
}

const props = defineProps({
    title: String,
    iconURL: String,
    skillType: {
        type: String as PropType<SkillType>,
        required: true
    }
});

const isDarkMode = useState("isDarkMode", () => false);
const backgroundColor = computed(() => isDarkMode.value ? 'var(--dark-accent-color)' : 'var(--accent-color)');
const borderColor = computed(() => props.skillType === SkillType.CS ? 'var(--cs-highlight-color)' : 'var(--es-highlight-color)');

</script>

<template>
    <div class="chip px-4 py-1 rounded-md flex items-center"
        :style="`background-color: transparent; transition: background-color 300ms; border: solid 1px ${borderColor}`">
        <img v-if="props.iconURL" :src="iconURL" alt="icon" class="mr-2" style="height: 1.3em">
        <div>{{ title }}</div>
    </div>
</template>

<style scoped>
.chip {
    box-shadow: 2px 2px 2px 0px rgba(0, 0, 0, 0.4);
}
</style>