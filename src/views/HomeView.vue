<template>
  <main>
    <SliderSection attr="slider__wrap score section" />
    <IntroSection attr="intro__wrap core3 section  bg-blue" />
    <PortSection attr="port__wrap core3 section center" />
    <YoutubeSection attr="youtube__wrap core3 section bg-blue" />
    <UnsplashSection attr="unsplash__wrap core3 section " />
    <MovieSection attr="movies__wrap core3 section bg-blue" />
  </main>
</template>

<script>
import SliderSection from "@/components/section/SliderSection.vue";
import IntroSection from "@/components/section/IntroSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";

export default {
  components: {
    IntroSection,
    SliderSection,
    PortSection,
    MovieSection,
    YoutubeSection,
    UnsplashSection,
  },
};
</script>
