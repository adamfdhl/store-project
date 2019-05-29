<template>
  <div class="card">
    <slot name="itemName"></slot>
    <hr>
    <slot name="itemDescription"></slot>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.card {
  border: 1px solid rgb(133, 131, 131);
  max-width: 250px;
  text-align: center;
  margin: 10px;
  cursor: pointer;
  -webkit-box-shadow: 0px 10px 30px -12px rgba(0, 0, 0, 0.68);
  -moz-box-shadow: 0px 10px 30px -12px rgba(0, 0, 0, 0.68);
  box-shadow: 0px 10px 30px -12px rgba(0, 0, 0, 0.68);
}

.card:hover {
  transform: scale(1.1);
}

hr {
  width: 90%;
}
</style>

