<template>
  <div id="app">
    <tool-bar></tool-bar>
    <spinner-test :loading="loadingState"></spinner-test>
    <transition name="page">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import ToolBar from './components/ToolBar.vue';
import SpinnerTest from './components/SpinnerTest.vue';
import bus from './utils/bus.js';

export default {
  components: {
    ToolBar,
    SpinnerTest
  },
  data() {
    return {
      loadingState: false,
    }
  },
  methods: {
    startSpinner() {
      this.loadingState = true;
    },
    endSpinner() {
      this.loadingState = false;
    }
  },
  created() {
    bus.$on('start:spinner', this.startSpinner);
    bus.$on('end:spinner', this.endSpinner);
  },
  beforeDestroy() {
    bus.$off('start:spinner', this.startSpinner)
    bus.$off('end:spinner', this.endSpinner);
  }
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
a {
  text-decoration: none;
  color: #34495e;
}
a:hover {
  color: #42b883;
  text-decoration: underline;
}
a.router-link-exact-active {
  text-decoration: underline;
}
.page-enter-active,
.page-leave-active {
  transition: opacity 0.5s ease;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
}
</style>
