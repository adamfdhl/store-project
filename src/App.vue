<template>
  <div id="app">
    <Navbar/>
    <Header/>
    <Content/>
  </div>
</template>
<script>
import Navbar from "./components/top/Navbar.vue";
import Header from "./components/top/Header.vue";
import Content from "./components/middle/Content.vue";
export default {
  name: "app",
  components: {
    Navbar,
    Header,
    Content
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
