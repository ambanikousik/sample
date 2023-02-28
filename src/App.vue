<template>
  <div class="main">
    <h1>Demo View Tree</h1>
    <vue-tree :node="root" />
  </div>
</template>

<script>
import VueTree from "./components/vueTree.vue";

export default {
  components: {
    VueTree,
  },
  data() {
    return {
      root: {
        name: "Main Folder",
        children: [
          { name: "music" },
          { name: "workspace" },
          { name: "New Folder" },
          { name: "Video" },
        ],
      },
    };
  },
};
</script>

<style scoped>
.main {
  /* padding: 20px; */
  font-size: x-large;
  font-weight: bold;
  /* text-align: center; */
}

h1 {
  background-color: aqua;
}
</style>
