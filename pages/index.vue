<script setup lang="ts">
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

enum SkillType {
    CS = "Computer Science",
    ES = "Entrepreneurship",
}

const skills = ref([
    { title: "HTML", iconURL: "/vector/html_icon.svg", skillType: SkillType.CS },
    { title: "CSS", iconURL: "/vector/css_icon.svg", skillType: SkillType.CS },
    { title: "TailwindCSS", iconURL: "/vector/tailwindcss_icon.svg", skillType: SkillType.CS },
    { title: "JavaScript", iconURL: "/vector/js_icon.svg", skillType: SkillType.CS },
    { title: "TypeScript", iconURL: "/vector/ts_icon.svg", skillType: SkillType.CS },
    { title: "Vue.js", iconURL: "/vector/vue_icon.svg", skillType: SkillType.CS },
    { title: "Nuxt.js", iconURL: "/vector/nuxt_icon.svg", skillType: SkillType.CS },
    { title: "Wordpress", iconURL: "/vector/wordpress_icon.svg", skillType: SkillType.CS },
    { title: "Python", iconURL: "/vector/python_icon.svg", skillType: SkillType.CS },
    { title: "Git", iconURL: "/vector/git_icon.svg", skillType: SkillType.CS },
    { title: "Docker", iconURL: "/vector/docker_icon.svg", skillType: SkillType.CS },
    { title: "Linux", iconURL: "/vector/linux_icon.svg", skillType: SkillType.CS },
    { title: "Design Thinking", skillType: SkillType.ES },
    { title: "Investing", skillType: SkillType.ES }
]);

const effort1active = ref(false);
const effort2active = ref(false);
const effort3active = ref(false);

let gsapContext: gsap.Context;

onMounted(() => {
    gsapContext = gsap.context(() => {
        gsap.registerPlugin(ScrollTrigger);
        gsap.to("#hero-section", {
            scrollTrigger: {
                trigger: "#hero-section",
            },
            duration: 1,
            opacity: 1,
        });
        gsap.to("#intro-div", {
            scrollTrigger: {
                trigger: "#intro-div",
            },
            duration: 1,
            delay: 0.5,
            opacity: 1,
        });
        gsap.to("#skills-div", {
            scrollTrigger: {
                trigger: "#skills-div",
            },
            duration: 1,
            delay: 0.5,
            opacity: 1,
        });
        gsap.to("#efforts-section", {
            scrollTrigger: {
                trigger: "#efforts-section",
            },
            duration: 1,
            delay: 0.5,
            opacity: 1,
        })
    });
});

onUnmounted(() => {
    gsapContext.revert();
});

</script>

<template>
    <main>
        <MySection id="hero-section" class="mb-32 opacity-0 flex flex-col justify-center items-center h-screen">
            <h1 class="text-center">HEY, I'M YORICK SCHILLING</h1>
            <p class="subtitle text-center">I am exploring the fields of <span
                    style="color: var(--cs-highlight-color)">Computer Science</span> and <span
                    style="color: var(--es-highlight-color)">Entrepreneurship</span> to
                develop innovative products that positively impact society, all while embracing growth and continuous
                learning.</p>
        </MySection>
        <MySection id="about-section" class="mb-64">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-64 lg:gap-16">
                <div id="intro-div" class="opacity-0">
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
                <div id="skills-div" class="opacity-0">
                    <h2 class="text-2xl font-extrabold mb-4">Skillset Overview</h2>
                    <ul class="flex flex-wrap">
                        <li v-for="(skill, index) in skills" :key="index" class="mr-4 mb-4">
                            <SkillsetChip :title="skill.title" :iconURL="skill.iconURL" :skillType="skill.skillType" />
                        </li>
                    </ul>
                </div>
            </div>
        </MySection>
        <MySection id="efforts-section" class="mb-64 opacity-0">
            <div class="flex flex-col items-center">
                <h2 class="text-2xl font-extrabold mb-4">My current Efforts</h2>
                <MyDivider width="128px" class="mb-4" />
                <p class="text-lg md:text-xl text-center">These things keep me the most occupied at the moment</p>
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
                    <p class="font-light">Visions Development is a web agency I founded with a good friend of mine. It
                        kinda happened naturally. Some people in my circle asked me, if I could build a website for them
                        and after 1-2 projects I told a friend about it and since my expertise is more on the technical
                        side and his more on the design side, we decided to team up and founded Visions Development. We
                        are eager to grow and learn, while working hard to build great experiences.</p>
                    <div class="self-end mt-auto font-medium"><span style="color: var(--cs-highlight-color)">Computer
                            Science</span> &nbsp;&&nbsp; <span
                            style="color: var(--es-highlight-color)">Entrepreneurship</span></div>
                </div>
                <div v-show="effort3active"
                    class="expanded_effort text-white flex flex-col p-6 fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-20"
                    style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('/img/ffi_logo.jpg'), linear-gradient(90deg, #fe7446, #fe7446 25%, #f74162 75%, #f74162)">
                    <button @click="effort3active = false" class="text-xl self-end">X</button>
                    <h3 class="text-2xl font-bold mb-2">Future Founders Initiative</h3>
                    <p class="font-light">The Future Founders Initiative is a non-profit organization whichs mission is
                        to inspire and educate young people to become entrepreneurs. I was part of the founding process
                        in 2024 and since them I am responsible for the technical side of things. For example I built
                        the website and the backend for the FFI platform.</p>
                    <div class="self-end mt-auto font-medium" style="color: var(--es-highlight-color)">Entrepreneurship
                    </div>
                </div>
            </div>
        </MySection>
    </main>
</template>

<style scoped>
h1 {
    font-size: clamp(36px, 6vw, 64px);
}

.subtitle {
    font-size: clamp(18px, 2vw, 24px);
}

.effort {
    width: 200px;
    height: 200px;
}

.expanded_effort {
    width: 90%;
    height: 60%;
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    box-shadow: 0px 6px 16px 0px rgba(0, 0, 0, 0.4);
}

@media screen and (min-width: 768px) {
    .expanded_effort {
        width: 664px;
        height: 374px;
    }
}
</style>