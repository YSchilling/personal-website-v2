<script setup>

const props = defineProps({ width: String })
const isDarkMode = useState("isDarkMode", () => false);

</script>

<template>
    <div
        :style="`background-color: ${isDarkMode ? 'var(--dark-text-color)' : 'var(--text-color)'}; width: ${props.width}; height: 2px; transition: background-color 300ms`">
    </div>
</template>