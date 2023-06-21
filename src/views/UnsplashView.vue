<template>
  <ContTitle title="Unsplash" />
  <UnsplashSlider />
  <UnsplashSearch />
  <UnsplashTag />
  <UnsplashCont :unsplashs="unsplashs" />
</template>
<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSearch from "@/components/unslpash/UnsplashSearch.vue";
import UnsplashSlider from "@/components/unslpash/UnsplashSlider.vue";
import UnsplashTag from "@/components/unslpash/UnsplashTag.vue";
import UnsplashCont from "@/components/unslpash/UnsplashCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSearch,
    UnsplashSlider,
    UnsplashTag,
    UnsplashCont,
  },

  setup() {
    const unsplashs = ref([]);
    const TopunSplash = async () => {
      await fetch(
        "https://api.unsplash.com/photos?client_id=q4jTUmJ2a6QDkRQyd2bInVsO-8Qz82CM8FWqW8l-jMk&per_page=30"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          unsplashs.value = result;
        })
        .catch((error) => console.log("error", error));
    };
    TopunSplash();
    return {
      TopunSplash,
      unsplashs,
    };
  },
};
</script>
