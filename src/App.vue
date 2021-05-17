<template>
  <v-app>
    <v-main>
      <h1>Hello world</h1>
      <video-player :options="videoOptions" />
    </v-main>
  </v-app>
</template>

<script>
import VideoPlayer from "./components/videoPlayer";
import "@videojs/http-streaming";

export default {
  name: "App",
  components: {
    VideoPlayer,
  },
  data: () => ({
    videoOptions: {
      autoplay: true,
      controls: true,
      sources: [
        {
          src:
            "https://hls-bucket-prototype.s3-eu-west-1.amazonaws.com/big_buck_bunny_720p_30mb.m3u8",
          type: "application/x-mpegURL",
        },
      ],
    },
  }),
};
</script>
