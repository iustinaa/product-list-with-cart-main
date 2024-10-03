<script setup>
import { reactive, ref } from "vue";
import productItem from "@/components/productItem.vue";
import rahat from "@/data.json"; // this automatically converts a json to a js array/object

const products = ref(rahat);
const cart = reactive([]); // new empty reactive array for vue

  // Define a reactive variable for the cart count
const cartCount = ref(0);

// Define a method to increment the cart count
const addToCart = (name, price) => {
  // console.log(name, price)
  cartCount.value++;
  cart.push([name, price]);
  console.log(cart);
};

const removeFromCart = (product) => {
  const index = this.cart.indexOf(product);
    if (index > -1) {
      this.cart.splice(index, 1);
    }
}

  // console.log();

</script>

<template>
  <div class="products">
    <main class="products__list">
      <h1 class="red-hat-text-bold">Desserts</h1>
      <div>
        <!-- it goes for each product from the json and renders the component , key is a vue magic thing to make sure reactivity / rendering works without issue -->
        <productItem v-for = "product in products" 
          :key="product.name"
          :image="product.image"
          :category="product.category" 
          :name="product.name"
          :price="product.price"
          @addToCart="addToCart"
          />
      </div>
    </main>
    <aside class="products__cart">
        <h1 class="red-hat-text-bold">Your Cart({{ cartCount }})</h1>
        <ul>
          <li v-for="product in cart" :key="product[0]" @addToCart="addToCart">
            {{ product[0]}} - {{ product[1]}}
            <button @click="removeFromCart(product)">Remove</button>
          </li>
        </ul>
        <div>
          <img src="./assets/images/illustration-empty-cart.svg" alt="Empty cart">
          <p class="red-hat-text-semibold">Your added items will appear here</p>
        </div>
    </aside>
  </div>
</template>

