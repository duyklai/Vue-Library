<template>
  <div id="app">
    <header>
      <h1>Library</h1>
    </header>
    <Library />
  </div>
</template>

<script>
import Library from "./components/Library.vue";

export default {
  name: "app",
  components: {
    Library
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");

#app {
  font-family: "Montserrat", sans-serif;
  margin-top: 60px;
}

body {
  background-color: #585858;
}

header {
  text-align: center;
}

header h1 {
  font-size: 40px;
  color: #ffa71a;
  text-shadow: 3px 3px black;
}
</style>
