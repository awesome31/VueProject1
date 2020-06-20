<template>
  <div class="container">
    <SearchBar @termChange="onTermChange" />
    <div class="row">
      <VideoDetail :video="selectedVideo" />
      <VideoList :videos="videos" @itemClick="onItemClick" />
    </div>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";
import { getVidoes } from "./api/youtube";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  data: () => ({
    videos: [],
    selectedVideo: null
  }),
  methods: {
    onTermChange(e) {
      getVidoes(e).then(res => {
        this.videos = res.data.items;
      });
    },
    onItemClick(item) {
      this.selectedVideo = item;
    }
  }
};
</script>