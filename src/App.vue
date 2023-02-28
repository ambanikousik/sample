<template>
  <section>
    <div class="main">
      <h1>Demo View Tree</h1>
    </div>
    <div @click="nodeClicked" class="root">
      <p>Root</p>
      <div class="icon">{{ expended ? "&minus;" : "&plus;" }}</div>
    </div>
    <section v-if="expended" class="child">
      <div style="display: flex; flex-direction: row; align-items: center">
        <div class="connector"></div>
        <p class="design">child-1</p>
      </div>
      <div style="display: flex; flex-direction: row; align-items: center">
        <div class="connector"></div>
        <p class="design">child-2</p>
      </div>
      <div style="display: flex; flex-direction: row; align-items: center">
        <div class="connector"></div>
        <p class="design">child-3</p>
      </div>
    </section>
  </section>
</template>

<script>
export default {
  name: "vueTree",
  data() {
    return {
      expended: true,
    };
  },
  methods: {
    nodeClicked() {
      this.expended = !this.expended;
    },
  },
};

// import VueTree from "./components/vueTree.vue";

// export default {
//   components: {
//     VueTree,
//   },
//   data() {
//     return {
//       root: {
//         name: "Main Folder",
//         children: [
//           { name: "music" },
//           { name: "workspace" },
//           { name: "New Folder" },
//           { name: "Video" },
//         ],
//       },
//     };
//   },
// };
</script>

<style scoped>
.connector {
  border: 1px solid #ccc;
  width: 10px;
  height: 0px;
}
.design {
  margin-left: 16px;
}
.main {
  font-size: x-large;
  font-weight: bold;
}

h1 {
  background-color: aqua;
}
.root {
  margin-top: 15px;
  margin-left: 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.child {
  margin-left: 20px;
  border-left: 2px solid #ccc;
}

.icon {
  height: 16px;
  width: 16px;
  margin-left: 130px;
  border: solid 0.5px #ccc;
  border-radius: 4px;
  display: flex;
  justify-content: center;
}
</style>
