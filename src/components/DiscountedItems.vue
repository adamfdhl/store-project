<template>
  <div class="container">
    <h2>Ramadhan sale! From 30% up to 85%!</h2>
    <div class="items-container">
      <CardItem v-for="product in discountedItems" :key="product.id">
        <template v-slot:itemName>
          <h3>{{ product.title }}</h3>
        </template>
        <template v-slot:itemDescription>
          <p>{{ product.body | snippets }}</p>
        </template>
      </CardItem>
    </div>
  </div>
</template>
<script>
import CardItem from "./CardItem.vue";
import axios from "axios";
export default {
  components: {
    CardItem
  },
  data() {
    return {
      discountedItems: []
    };
  },
  filters: {
    snippets(value) {
      return value.toString().slice(0, 100) + "... (click to read more)";
    }
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/posts").then(response => {
      this.discountedItems = response.data;
      this.discountedItems = this.discountedItems.slice(0, 10);
    });
  }
};
</script>
<style lang="scss" scoped>
.items-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f8f8f8;
}
</style>