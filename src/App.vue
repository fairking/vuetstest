<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld
      ref="helloWorld"
      msg="Welcome to Your Vue.js + TypeScript App"
    />
    <input type="button" value="Click me" @click="onClick" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import HelloWorld from "./components/HelloWorld.vue";
type HelloWorldType = InstanceType<typeof HelloWorld>;

export default Vue.extend({
  name: "App",
  components: {
    HelloWorld,
  },
  methods: {
    onClick(e: Event): void {
      console.log(e);
      const helloWorld = this.$refs.helloWorld as HelloWorldType;
      helloWorld.appendDate();
      // The following line will throw a compilation error
      // helloWorld.appendDate2();
    },
  },
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
