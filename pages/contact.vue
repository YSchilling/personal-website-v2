<script setup>

const isDarkMode = useState("isDarkMode", () => false);

useHead({ title: null })

</script>

<template>
  <main class="flex items-center">
    <MySection class=" flex flex-col justify-center items-center">
      <div class="flex flex-col items-center">
        <h1>CONTACT</h1>
        <MyDivider width="80%" class="mb-6" />
      </div>
      <div class="flex flex-col md:grid grid-cols-3 grid-rows-2 gap-2">
        <a href="mailto:contact@yorickschilling.com"
          class="col-span-2 border rounded-md p-4 flex items-center duration-300 hover:scale-105">
          <img :src="isDarkMode ? '/img/mail_dark.png' : '/img/mail.png'" width="36px" height="36px" class="mr-2">
          <div>contact@yorickschilling.com</div>
        </a>
        <a href="https://linkedin.com/in/yschilling" target="_blank"
          class="hidden row-span-2 md:flex justify-center items-center duration-300 hover:scale-105">
          <img src="/img/linkedin.png" width="148px" height="148px">
        </a>
        <a href="https://linkedin.com/in/yschilling" target="_blank"
          class="md:hidden col-span-3 md:col-span-2 border rounded-md p-4 flex items-center duration-300 hover:scale-105">
          <img src="/img/linkedin.png" width="32px" height="32px" class="ml-1 mr-2 rounded-md">
          <div>LinkedIn</div>
        </a>
        <a href="https://github.com/yschilling" target="_blank"
          class="col-span-2 border rounded-md p-4 flex items-center duration-300 hover:scale-105">
          <img :src="isDarkMode ? '/vector/github-mark-white.svg' : '/vector/github-mark.svg'" width="32px"
            height="32px" class="ml-1 mr-2">
          <div>GitHub</div>
        </a>

      </div>
    </MySection>
  </main>
</template>

<style scoped>
h1 {
  font-size: clamp(32px, 6vw, 48px);
}
</style>