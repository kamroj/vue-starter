<template>
  <div id="app">
    <div v-if="loginPage == false">
      Zalogowano {{email}}
      <button @click="proceedIntoNextSite()">Wróć</button>
    </div>
    <div v-else>
      <h1>Pseudo logowanie</h1>
      Zaloguj się na emial:
      <input type="text" v-model="email">

      <button @click="proceedIntoNextSite()">Zaloguj</button>
    </div>
  </div>
</template>

<script>
import "milligram";

export default {
  data() {
    return {
      loginPage: true,
      email: "heheszki@op.pl"
    };
  },
  methods: {
    proceedIntoNextSite() {
      this.loginPage = this.loginPage === false;
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
