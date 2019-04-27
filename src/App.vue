<template>
  <div id="app">
    <div v-if="loginPage == false">
      Zalogowano {{email}}
      <button @click="proceedIntoNextSite()">Wróć</button>
    </div>
    <div v-else>
      <login-form @login="logMeIn($event)"></login-form>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},
  data() {
    return {
      loginPage: true,
      email: "heheszki@op.pl"
    };
  },
  methods: {
    proceedIntoNextSite() {
      this.loginPage = true;
    },
    logMeIn(username) {
      this.email = username;
      this.loginPage = false;
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
