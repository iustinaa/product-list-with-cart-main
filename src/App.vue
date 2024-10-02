<script setup>
import { ref } from "vue";
import productItem from "@/components/productItem.vue";
import rahat from "@/data.json"; // this automatically converts a json to a js array/object

  const products = ref(rahat);

  console.log();

</script>

<template>
  <div class="products">
    <main class="products__list">
      <h1 class="red-hat-text-bold">Desserts</h1>
      <div>
        <!-- it goes for each product from the json and renders the component , key is a vue magic thing to make sure reactivity / rendering works without issue -->
        <productItem v-for = "product in products" :key="product.name" :image="product.image"
        :category="product.category" :name="product.name" :price="product.price" />
      </div>
    </main>
    <aside class="products__cart">
        <h1 class="red-hat-text-bold">Your Cart(0)</h1>
        <div>
          <img src="./assets/images/illustration-empty-cart.svg" alt="Empty cart">
          <p class="red-hat-text-semibold">Your added items will appear here</p>
        </div>
    </aside>
  </div>
</template>

