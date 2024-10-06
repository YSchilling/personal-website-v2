<script setup>

const skills = ref(["HTML", "CSS", "TailwindCSS", "JavaScript", "Vue.js", "Nuxt.js", "Python", "Git", "Docker", "Linux"]);

const effort1active = ref(false);
const effort2active = ref(false);
const effort3active = ref(false);

function activateEffort(element) {
    element.style.width = "664px";
    element.style.height = "374px";
    element.style["background-color"] = "#183859";
    element.classList.add("saturate-100");
    element.querySelector("img").style.filter = "brightness(0.5)";
    console.log(element.style);
}

</script>

<template>
    <main>
        <MySection class="flex flex-col justify-center items-center h-screen">
            <h1>HEY, I'M YORICK SCHILLING</h1>
            <p class="text-xl text-center">I am exploring the fields of <span
                    style="color: var(--cs-highlight-color)">Computer Science</span> and <span
                    style="color: var(--es-highlight-color)">Entrepreneurship</span> to
                develop innovative products <br> that
                positively impact society, all while embracing <br>growth and continuous learning.</p>
        </MySection>
        <MySection class="mt-32">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
                <div>
                    <h2 class="text-2xl font-extrabold mb-4">Short Introduction</h2>
                    <p>With a lifelong passion for technology, I have immersed myself in the world of computers and
                        programming. What began as a hobby five years ago has become a professional journey, where I’ve
                        spent the past year honing my skills in the industry. Currently pursuing a degree in Computer
                        Science at the prestigious Technical University of Munich (TUM), I thrive on tackling complex
                        challenges and developing innovative solutions.
                        <br><br>
                        My entrepreneurial spirit fuels my ambition to launch my own venture, where I can merge my
                        technical expertise with a vision for creating impactful products that contribute to a brighter
                        future. I am always eager to learn and grow, actively seeking out opportunities that expand my
                        horizons both personally and professionally.
                    </p>
                </div>
                <div>
                    <h2 class="text-2xl font-extrabold mb-4">Skillset Overview</h2>
                    <ul class="flex flex-wrap">
                        <li v-for="skill in skills" :key="skill" class="mr-4 mb-4 bg-gray-200 px-4 py-1 rounded-md">{{
                            skill
                            }}
                        </li>
                    </ul>
                </div>
            </div>
        </MySection>
        <MySection class="my-96">
            <div class="flex flex-col items-center">
                <h2 class="text-2xl font-extrabold mb-4">My current Efforts</h2>
                <MyDivider width="128px" class="mb-4" />
                <p class="text-xl">These things keep me the most occupied at the moment</p>
                <div class="mt-12 flex flex-col md:flex-row gap-8">
                    <img @click="effort1active = true" src="/img/tum_logo.png" width="200px" height="200px"
                        class="effort saturate-0 duration-300 hover:saturate-100 hover:cursor-pointer">
                    <img @click="effort2active = true" src="/vector/visions_logo.svg" width="200px" height="200px"
                        class="effort bg-neutral-600 duration-300 hover:bg-black  hover:cursor-pointer px-4">
                    <img @click="effort3active = true" src="/img/ffi_logo.jpg" width="200px" height="200px"
                        class="effort saturate-0 duration-300 hover:saturate-100  hover:cursor-pointer">
                </div>
                <div v-show="effort1active || effort2active || effort3active"
                    class="fixed top-0 left-0 w-screen h-screen z-10" style="background-color: rgba(0,0,0,0.5)"></div>
                <!-- expanded efforts -->
                <div v-show="effort1active"
                    class="expanded_effort text-white flex flex-col p-6 fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-20"
                    style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('/img/tum_logo.png'), linear-gradient(#3070b3, #3070b3)">
                    <button @click="effort1active = false" class="text-xl self-end">X</button>
                    <h3 class="text-2xl font-bold mb-2">Technical University of Munich</h3>
                    <p class="font-light">I am currenty pursuing a degree in Computer Science at the prestigious
                        Technical University of Munich (TUM). So far I am very happy with my choice. The TUM has a
                        strong focus on technology and entrepreneurship, which exactly represents my current interests.
                        I plan on graduating in 2027.</p>
                    <div class="self-end mt-auto font-medium" style="color: var(--cs-highlight-color)">Computer
                        Science
                    </div>
                </div>
                <div v-show="effort2active"
                    class="expanded_effort text-white flex flex-col p-6 fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-20"
                    style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('/img/visions_logo.png'), linear-gradient(#000000, #000000)">
                    <button @click="effort2active = false" class="text-xl self-end">X</button>
                    <h3 class="text-2xl font-bold mb-2">Visions Development</h3>
                    <p class="font-light">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
                        eirmod tempor
                        invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
                        accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata
                        sanctus est Lorem ipsum dolor sit amet.</p>
                    <div class="self-end mt-auto font-medium"><span style="color: var(--cs-highlight-color)">Computer
                            Science</span> &nbsp;&&nbsp; <span
                            style="color: var(--es-highlight-color)">Entrepreneurship</span></div>
                </div>
                <div v-show="effort3active"
                    class="expanded_effort text-white flex flex-col p-6 fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-20"
                    style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('/img/ffi_logo.jpg'), linear-gradient(90deg, #fe7446, #fe7446 25%, #f74162 75%, #f74162)">
                    <button @click="effort3active = false" class="text-xl self-end">X</button>
                    <h3 class="text-2xl font-bold mb-2">Future Founders Initiative</h3>
                    <p class="font-light">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
                        eirmod tempor
                        invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
                        accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata
                        sanctus est Lorem ipsum dolor sit amet.</p>
                    <div class="self-end mt-auto font-medium" style="color: var(--es-highlight-color)">Entrepreneurship
                    </div>
                </div>
            </div>
        </MySection>
    </main>
</template>

<style scoped>
h1 {
    font-size: 64px;
}

.effort {
    width: 200px;
    height: 200px;
}

.expanded_effort {
    width: 664px;
    height: 374px;
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    box-shadow: 0px 6px 16px 0px rgba(0, 0, 0, 0.4);
}
</style>