<script>
import Roadmap from '~/components/data-display/Roadmap.vue'

export default {
  name: "AboutPage",
  components: {
    Roadmap,
  },
  async asyncData({ $content }) {
    const aboutPage = await $content("about").fetch();
    return {
      aboutPage,
    };
  },
};
</script>

<template>
  <article class="w-auto prose">
    <img class="hidden w-52 mt-20 float-right md:block" src="~/static/FTProfile.webp" alt="Hi_I'm_Cim Farm Together Avatar"/>
    <nuxt-content :document="aboutPage" />
    <Roadmap class="mx-4"/>
  </article>
</template>