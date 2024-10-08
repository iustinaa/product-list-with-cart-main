<template>
    <div class="modal__order_confirmed">
        <div class="model__order_confirmed-content">
            <h1 class="red-hat-text-bold">Order Confirmed</h1>
            <p>We hope you enjoy your food!</p>
            <div>
                <ul class="red-hat-text-bold">
                <li v-for="product in cart" :key="product[0]" @addToCart="addToCart">
                <span class="products__list__item-title red-hat-text-semibold">{{ product[0] }}</span> <!-- Product name in a span -->
                <span class="">{{ product[1] }}</span> <!-- Product price in a span -->
                </li>
            </ul>
            
            <p>Order Total <span>{{ totalCost }}</span></p>
            </div>
            <button class="order close" @click="$emit('close')">Start New Order</button><!--@click="$emit('close')" means that when you click on this button, it will emit a custom event called close. This is used to communicate back to the parent component, which can then react by hiding the modal. It's the mechanism that lets the user close the modal when they're done with it.-->
        </div>
    </div>
</template>

<script setup>
const { cart, totalCost } = defineProps(['cart', 'totalCost']);// defining cart as a prop in a Vue 3 component. This setup allows the component to receive the cart data from its parent component. So, orderConfirmedModal can access and display the cart information passed down to it.

</script>