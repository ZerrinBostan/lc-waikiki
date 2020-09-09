<template>
  <div id="app" class="container">
    <div class="login-wrapper">
      <Login />
    </div>
  </div>
</template>

<script>
import { Login } from "./components";
import "es6-promise/auto";
import store from "./store";

export default {
  name: "App",
  store,
  components: {
    Login
  }
};
</script>

<style lang="scss">
#app {
  font-family: Open Sans, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
}
</style>
