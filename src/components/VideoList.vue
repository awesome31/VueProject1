<template>
  <ul class="list-group col-md-4">
    <VideoListItem
      :key="video.id.videoId"
      :video="video"
      v-for="video in videos"
      @itemClick="onItemClick"
    />
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";

export default {
  name: "VideoList",
  components: { VideoListItem },
  props: {
    videos: Array
  },
  methods: {
    onItemClick(item) {
      this.$emit("itemClick", item);
    }
  }
};
</script>

<style scoped>
</style>
