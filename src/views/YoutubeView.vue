<template>
  <ContTitle title="Youtube" />
  <YoutubeSearch />
  <YoutubeSlider />
  <YoutubeTag />
  <YoutubeCont :youtubes="youtubes" />
</template>
<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const youtubes = ref([]);

    const TopYoutube = async () => {
      await fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=tennis&key=AIzaSyBTyYekqKdJKfjwf6aUYLwTbtRLG_jR2H8"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };
    TopYoutube();
    return {
      TopYoutube,
      youtubes,
    };
  },
};
</script>
