<template>
    <div class="product-list">
      <h2>Item List</h2>
      <div class="product-container">
        <ProductItem 
          v-for="product in products" 
          :key="product.id" 
          :product="product" 
          @add-to-cart="handleAddToCart" 
        />
      </div>
  
      <div class="cart">
        <h2>Cart:</h2>
        <ul>
          <li v-for="item in cart" :key="item.id">
            {{ item.name }} - ₱{{ item.price }}
          </li>
        </ul>
        <h3>Total: ₱{{ total }}</h3>
      </div>
    </div>
  </template>
  
  <script>
  import Item from './Item.vue';
  
  export default {
    components: {
      Item,
    },
    data() {
      return {
        products: [
          { id: 1, name: 'Item 1', price: 100 },
          { id: 2, name: 'Item 2', price: 150 },
          { id: 3, name: 'Item 3', price: 300 },
        ],
        cart: [],
      };
    },
    computed: {
      total() {
        return this.cart.reduce((sum, item) => sum + item.price, 0);
      },
    },
    methods: {
      handleAddToCart(product) {
        this.cart.push(product);
      },
    },
  };
  </script>
  
  <style scoped>
  .product-list {
    padding: 10px;
  }
  .cart {
    margin-top: 20px;
  }
  </style>
