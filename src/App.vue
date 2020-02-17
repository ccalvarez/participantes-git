<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <ul>
      <li v-for="participante in participantes">
        <img :src="getIdenticonURL(participante.github)" alt />
        {{ participante.name }}
      </li>
    </ul>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import participantes from "@/assets/data/participantes.json";

export default {
  name: "App",
  data: function() {
    return {
      participantes: participantes
    };
  },
  components: {
    HelloWorld
  },
  methods: {
    getIdenticonURL(username) {
      return `https://github.com/identicons/${username}.png`;
    }
  }
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
