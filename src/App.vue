<template>
  <div>
    <button @click="showComp">show</button>
    <div v-if="show">
      <LoaderComp />
    </div>
  </div>
</template>

<script>
import LoaderComp from "./components/LoaderComp.vue"
import LoadingComp from "./components/LoadingComp.vue";
import ErrorComp from "./components/ErrorComp.vue";
// import { defineAsyncComponent } from '@vue/runtime-core';
// const LoaderComp = defineAsyncComponent({
//   // the loader function
//   loader: () => import('./components/LoaderComp.vue'),

//   // A component to use while the async component is loading
//   loadingComponent: LoadingComp,
//   // Delay before showing the loading component. Default: 200ms.
//   delay: 200,

//   // A component to use if the load fails
//   errorComponent: ErrorComp,
//   // The error component will be displayed if a timeout is
//   // provided and exceeded. Default: Infinity.
//   timeout: 1000
// })
export default {
  name: "App",
  data() {
    return {
      show: false,
    };
  },
  components: {
    LoaderComp,LoadingComp,ErrorComp
  },
  methods: {
    showComp() {
      this.show = true;
    },
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
