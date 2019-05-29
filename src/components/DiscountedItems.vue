<template>
  <div class="container">
    <h2>Ramadhan sale! From 30% to 85%!</h2>
    <CardItem v-for="product in products" :key="product.id">
      <template v-slot:itemName>
        <h3>{{ product.title }}</h3>
      </template>
      <template v-slot:itemDescription>
        <p>{{ product.body | snippets }}</p>
      </template>
    </CardItem>
  </div>
</template>
<script>
import CardItem from "./CardItem.vue";
import axios from "axios";
export default {
  components: {
    CardItem
  }
};
</script>
<style scoped>
</style>
