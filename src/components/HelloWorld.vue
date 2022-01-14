<template>
  <div class="hello">
    <p :title="msg">
      {{ test }}
    </p>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "HelloWorld",
  props: {
    msg: { type: String, required: true },
  },
  data() {
    return {
      test: "abc",
    };
  },
  methods: {
    appendDate(): string {
      this.test = "abc " + new Date().toLocaleTimeString();
      return this.test;
    },
  },
});
</script>

<style scoped lang="scss">
$blue: rgb(79, 135, 255);
.hello {
  background: $blue;
  p {
    padding: 0.5cm;
  }
}
</style>
