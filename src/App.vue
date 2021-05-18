<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <JsonForms data="{}" v-bind:renderers="renderers" v-bind:schema="schema" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import { JsonForms } from "@jsonforms/vue2";
import testRenderer from "./TestRenderer.vue";

const renderers = [{ tester: () => 1, renderer: testRenderer }];

const schema = {
  properties: {
    name: {
      type: "string",
      minLength: 1,
      description: "The task's name",
    },
  },
};

export default Vue.extend({
  name: "App",
  components: {
    JsonForms,
  },
  data() {
    return {
      renderers,
      schema,
    };
  },
});
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
