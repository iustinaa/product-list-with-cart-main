<template>
    <article class="products__list__item">
      <div class="products__list__item-image">
        <img :src="mobileImage" :srcset="`${mobileImage} 769w, ${tabletImage} 992w, ${desktopImage} 1200w`" alt="Waffle with Berries">
        <button><img src="../assets/images/icon-add-to-cart.svg" alt="Add to Cart"><span>Add to Cart</span></button>
      </div>

      <div class="products__list__item-category red-hat-text-regular">{{props.category}}</div>
        <h2 class="products__list__item-title red-hat-text-semibold">{{props.name}}</h2>
      <div class="products__list__item-price red-hat-text-bold">${{props.price}}</div>
    </article>
</template>
<script setup>
const props = defineProps(['image','name', 'price', 'category'])
console.log(props.image);

const mobileImage = new URL(props.image.mobile, import.meta.url);
const tabletImage = new URL(props.image.tablet, import.meta.url);
const desktopImage = new URL(props.image.desktop, import.meta.url);
</script>