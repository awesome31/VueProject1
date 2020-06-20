<template>
  <li class="list-group-item media" @click="onItemClick">
    <img :src="getThumbnail" class="mr-3" />
    <div class="media-body">{{video.snippet.title}}</div>
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    getThumbnail() {
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onItemClick() {
      this.$emit("itemClick", this.video);
    }
  }
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
}

li:hover {
  background-color: #eeeeee;
}
</style>