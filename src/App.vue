<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <JsonForms data="{}" v-bind:renderers="renderers" v-bind:schema="schema" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { JsonForms } from "@jsonforms/vue2";
import { vanillaRenderers } from "@jsonforms/vue2-vanilla";

const renderers = [...vanillaRenderers];

const schema = {
  properties: {
    name: {
      type: "string",
      minLength: 1,
      description: "The task's name",
    },
  },
};

@Component({
  components: {
    JsonForms,
  },
  data() {
    return {
      renderers,
      schema,
    };
  },
})
export default class App extends Vue {}
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
