<template>
  <div id="app">
    <Navbar/>
    <Header/>
  </div>
</template>
<script>
import Navbar from "./components/top/Navbar.vue";
import Header from "./components/top/Header.vue";
export default {
  name: "app",
  components: {
    Navbar,
    Header
  }
};
</script>

<style>
body {
  margin: 0;
}

#app {
}
</style>
