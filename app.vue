<script setup>

const isDarkMode = useState("isDarkMode", () => false);


watch(() => isDarkMode, () => {
  console.log("watch executed")
  document.querySelector("body").style.backgroundColor = isDarkMode ? "#121212" : "#f9f9f9";
});

</script>

<template>
  <div class="duration-500" :style="`background-color: ${isDarkMode ? 'var(--dark-bg-color)' : 'var(--bg-color)'};
  color: ${isDarkMode ? 'var(--dark-text-color)' : 'var(--text-color)'}`">
    <MyHeader />
    <NuxtPage />
  </div>
</template>

<style scoped></style>