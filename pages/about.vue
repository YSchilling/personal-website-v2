<script setup lang="ts">
import gsap from "gsap";
import { TextPlugin } from "gsap/TextPlugin";

const { data } = await useAsyncData('about_text', () => queryContent('/about_text').findOne())
const aboutText = data.value!.value;

const button = ref();

let gsapContext: gsap.Context;
let gsapTween: gsap.core.Tween;

onMounted(() => {
  gsapContext = gsap.context(() => {
    gsap.registerPlugin(TextPlugin);
    gsapTween = gsap.to("#text-container", {
      paused: true,
      text: {
        value: aboutText,
        speed: 2,
      }
    });
  });
});

onUnmounted(() => {
  gsapContext.revert();
});

</script>

<template>
  <MySection class="pt-48 flex flex-col items-center">
    <div class="flex flex-col items-center">
      <h1>MY STORY</h1>
      <MyDivider width="80%" class="mb-6" />
    </div>
    <button ref="button" @click="button.style.display = 'none'; gsapTween.play();"
      class="border px-3 py-1 rounded-md hover:scale-105 duration-300">Read
      Story</button>
    <div id="text-container"></div>
  </MySection>

</template>

<style scoped>
h1 {
  font-size: clamp(32px, 6vw, 48px);
}


#text-container {
  min-height: 50vh;
  margin: 0 0 16px 0;
  align-self: flex-start;
}

@media screen and (min-width: 768px) {
  #text-container {
    margin: 0 10% 16px 10%;
  }

}
</style>