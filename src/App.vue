<script setup>
import { reactive, ref, computed } from "vue";
import productItem from "@/components/productItem.vue";
import orderConfirmedModal from "@/components/orderConfirmedModal.vue";
import rahat from "@/data.json"; // this automatically converts a json to a js array/object

const products = ref(rahat);
const cart = reactive([]); // new empty reactive array for vue
const showModal = ref(false);//creates  a reactive reference showModal initialized to false.This means showModal is a reactive state variable that Vue will update the DOM for whenever its value changes. When showModal is set to true, it’ll trigger the modal to be shown, and setting it back to false will hide it again.

// Define a reactive variable for the cart count
const cartCount = ref(0);

// Define a method to increment the cart count
const addToCart = (name, price, image) => {

  const existingProduct = cart.findIndex(item => item[0] === name);


  console.log(existingProduct);
  // console.log(name, price)
  cartCount.value++;
  
  if (existingProduct != -1) {
    cart[existingProduct][3]++; 
  } else {
    cart.push([name, price, image, 1]);
  }
  
  
  console.log(cart);
};

const removeFromCart = (product) => {
  const index = cart.indexOf(product);
    if (index > -1) {
      cart.splice(index, 1);
      cartCount.value--;
    }
}

const totalCost = computed(() => {
  return cart.reduce((total, product) => {
    return total + product[1] * product[3];
  }, 0);
}); //The totalCost computed property calculates the total cost by iterating over the cart array and summing up the product prices multiplied by their quantities.

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
        <h1 class="red-hat-text-bold">Your Cart ({{ cartCount }})</h1>
        <div class="products__cart_empty" v-if="cart.length === 0"><!--The v-if directive is added to the products__cart_empty div. This directive will only render the div if the cart array is empty (cart.length === 0).-->
          <img src="./assets/images/illustration-empty-cart.svg" alt="Empty cart">
          <p class="red-hat-text-semibold">Your added items will appear here</p>
        </div>
        <div class="products__cart_added" v-if="cart.length >= 1">
          <ul>
            <li v-for="product in cart" :key="product[0]" @addToCart="addToCart">
              <span>{{ product[3] }}</span>
              <span class="products__list__item-title red-hat-text-semibold">{{ product[0] }}</span> <!-- Product name in a span -->
              <span class="">{{ product[1] }}</span> <!-- Product price in a span -->
              <button class="btn_remove" @click="removeFromCart(product)">
                <img src="./assets/images/icon-remove-item.svg" alt="Remove Product">
              </button>
            </li>
          </ul>
          <p>Order Total <span class="red-hat-text-bold">{{ totalCost }}</span></p><!--The total cost is displayed using the totalCost computed property.-->
          <p><img src="./assets/images/icon-carbon-neutral.svg" alt="Carbon Neutral">This is a <span class="red-hat-text-bold"> carbon-neutral</span> delivery</p>
          <button class="order" @click="showModal = true">Confirm Order</button>
          <orderConfirmedModal v-if="showModal" class="overlay" @close="showModal = false" :cart="cart" :totalCost="totalCost"/><!--The :cart="cart" part is binding a cart object as a prop to the orderConfirmedModal component. It’s saying, "Hey, modal, here’s the cart object you’ll need to display info."-->
        </div>
    </aside>

  </div>
</template>

