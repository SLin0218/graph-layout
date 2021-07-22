<template>
  <div id="app"></div>
</template>

<script>
import G6 from "@antv/g6";
import { edgeLayout } from "./util/layout.js";
import Data from "./data.js";

export default {
  name: "App",
  mounted() {
    this.graph = new G6.Graph({
      container: "app",
      width: window.innerWidth,
      height: window.innerHeight,
    });
    this.graph.read(Data.data1);
    edgeLayout(this.graph);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
