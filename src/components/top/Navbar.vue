<template>
  <div class="navbar">
    <li>Home</li>
    <li>About</li>
    <li>Login</li>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.navbar {
  list-style-type: none;
  background-color: skyblue;
  margin: 0;
}
.navbar li {
  display: inline-block;
  cursor: pointer;
  padding: 15px 20px;
}
.navbar li:hover {
  background-color: rgb(41, 91, 228);
}
</style>