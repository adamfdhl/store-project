<template>
  <div class="container">
    <h2>Ramadhan sale! From 30% up to 85%!</h2>
    <div class="card-carousel-wrapper">
      <div class="card-carousel--nav__left"/>

      <CardItem v-for="product in discountedItems" :key="product.id">
        <template v-slot:itemName>
          <h3>{{ product.title }}</h3>
        </template>
        <template v-slot:itemDescription>
          <p>{{ product.body | snippets }}</p>
        </template>
      </CardItem>

      <div class="card-carousel--nav__right"/>
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
      this.discountedItems = this.discountedItems.slice(0, 5);
    });
  }
};
</script>
<style lang="scss" scoped>
.card-carousel-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px 0 40px;
  color: #666a73;
}

.card-carousel {
  display: flex;
  justify-content: center;
  width: 640px;

  &--overflow-container {
    overflow: hidden;
  }

  &--nav__left,
  &--nav__right {
    display: inline-block;
    width: 15px;
    height: 15px;
    padding: 10px;
    box-sizing: border-box;
    border-top: 2px solid #42b883;
    border-right: 2px solid #42b883;
    cursor: pointer;
    margin: 0 10px;
    transition: transform 150ms linear;

    &[disabled] {
      opacity: 0.2;
      border-color: black;
    }
  }

  &--nav__left {
    transform: rotate(-135deg);
    &:active {
      transform: rotate(-135deg) scale(0.9);
    }
  }
  &--nav__right {
    transform: rotate(45deg);
    &:active {
      transform: rotate(45deg) scale(0.9);
    }
  }
}
</style>