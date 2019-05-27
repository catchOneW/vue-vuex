<template>
  <div id="app">
    {{name}}
    <div @click="add">+</div>
  </div>
</template>

<script>
import Vue from "vue";

import HelloWorld from "./components/HelloWorld";
var $store = new Vue({
  data: {
    state: {
      a: 1
    }
  },
  computed: {
    name() {
      return this.state.a + "computed";
    }
  },
  methods: {
    dispatch() {},
    commit() {},
    mapAction(fn) {
      fn(this.commit);
    },
    mapState(fn) {
      fn(this);
      return fn;
    }
  }
});
export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {};
  },
  computed: {
    name() {
      return $store.name;
    }
  },
  methods: {
    add() {
      $store.state.a += 1;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
