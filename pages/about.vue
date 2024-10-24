<script setup lang="ts">
useHead({ title: null })
</script>

<template>
  <main class="mb-64">
    <MySection class="pt-32 flex flex-col items-center">
      <div class="flex flex-col items-center">
        <h1>MY STORY</h1>
        <MyDivider width="80%" class="mb-6" />
      </div>
      <div class="text-base md:text-lg">My journey into tech started in high school with a Udemy course on Python. I
        remember sitting
        at my grandma's
        house on vacation, sneaking away at night to dive into the lessons while everyone else was asleep. That was when
        I
        discovered the exciting world of computer science. I explored many topics out of pure curiosity, even if I
        didn’t
        have the focus I needed back then. I was young and just starting out!<br><br>As I neared my A-levels, I wanted
        to
        connect with other motivated students. That’s when I found weekend courses at local universities. I was
        surprised
        by how many free options were available! I met amazing people and became interested in entrepreneurship—my
        second
        passion.<br><br>During my A-levels, I received a scholarship from the Stiftung der Deutschen Wirtschaft and
        participated in their six-month Entrepreneurship Talent Academy program. I had some experience in
        entrepreneurship
        from other events, but this program really reinforced my interest and helped me make lifelong
        friends.<br><br>After finishing my A-levels, I was eager to start a startup and make a difference. I teamed up
        with two friends, but our project fell apart after a few months due to shifting priorities in life. I took some
        time to focus on my personal life, while my career ambitions were on hold.<br><br>Everything changed in early
        2024
        when I landed an internship at BMW. I was excited but nervous, as I had only worked on personal projects before.
        Thankfully, I thrived in that environment and even received praise for my organized approach.<br><br>With my
        newfound confidence, I realized it was time to start programming professionally. When my dad asked me to build a
        website for a friend of his, I jumped at the opportunity—my first paid programming project!<br><br>Now, I’m
        pursuing a bachelor’s degree in computer science at TUM in Munich, working with my friend on a tech startup, and
        volunteering with the Future Founders Initiative to help aspiring entrepreneurs.<br><br>I’m excited to continue
        this journey and see where it takes me!</div>
    </MySection>
  </main>
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