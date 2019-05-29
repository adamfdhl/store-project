<template>
  <div class="populer-items">
    <h2>This Week Items!</h2>
    <div class="card-container">
      <CardItem v-for="product in products" :key="product.id">
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
import CardItem from "../CardItem.vue";
import axios from "axios";
export default {
  components: {
    CardItem
  },
  data() {
    return {
      products: []
    };
  },
  filters: {
    snippets(value) {
      return value.toString().slice(0, 100) + "... (click to read more)";
    }
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/posts").then(response => {
      this.products = response.data;
      this.products = this.products.slice(0, 3);
    });
  }
};
</script>
<style scoped>
.populer-items {
  text-align: center;
}

.card-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
</style>