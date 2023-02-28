<template>
  <div class="tree">
    <div @click="nodeClicked" class="root">
      {{ node.name }}
      <span v-if="hasChildren" class="icon">{{
        expended ? "&minus;" : "&plus;"
      }}</span>
    </div>

    <div class="child" v-if="expended">
      <vueTree v-for="child in node.children" :key="child.name" :node="child" />
    </div>
  </div>
</template>

<script>
export default {
  name: "vueTree",
  props: {
    node: Object,
  },
  data() {
    return {
      expended: false,
    };
  },
  methods: {
    nodeClicked() {
      this.expended = !this.expended;
    },
  },
  computed: {
    hasChildren() {
      return this.node.children;
    },
  },
};
</script>

<style scoped>
.root {
  margin-top: 15px;

}

.child {
  padding-left: 5px;
  margin-left: 20px;
  border-left: 2px solid #ccc;
}

.icon {
  margin-left: 130px;


}
</style>
