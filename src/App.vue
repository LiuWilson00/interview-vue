<template>
  <div id="app">
    <div>
      <button @click="question = 0">question 1</button>
      <button @click="question = 1">question 2</button>
    </div>

    <Home v-if="question == 0" msg="Welcome to Your Vue.js App" />
    <Bonus v-else />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Bonus from "./components/Bonus.vue";
export default {
  name: "App",
  data() {
    return {
      question: 0,
    };
  },
  components: {
    Home,
    Bonus,
  },
};
</script>

<style></style>
