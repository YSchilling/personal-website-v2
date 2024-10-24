<script setup>

const isDarkMode = useState("isDarkMode", () => false);


watch(() => isDarkMode, () => {
  console.log("watch executed")
  document.querySelector("body").style.backgroundColor = isDarkMode ? "#121212" : "#f9f9f9";
});

useHead({
  title: null,
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - Yorick Schilling` : "Yorick Schilling";
  }
})

</script>

<template>
  <div class="min-h-screen flex flex-col duration-500" :style="`background-color: ${isDarkMode ? 'var(--dark-bg-color)' : 'var(--bg-color)'};
  color: ${isDarkMode ? 'var(--dark-text-color)' : 'var(--text-color)'}`">
    <MyHeader />
    <div class="h-16"></div>
    <NuxtPage class="flex-grow" />
    <MyFooter />
  </div>
</template>

<style scoped></style>