<script setup>

</script>

<template>
  <div class="products">
    <main class="products__list">
      <h1 class="red-hat-text-bold">Desserts</h1>
      <div>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-waffle-mobile.jpg" srcset="./assets/images/image-waffle-mobile.jpg 769w, ./assets/images/image-waffle-tablet.jpg 992w, ./assets/images/image-waffle-desktop.jpg 1200w" alt="Waffle with Berries">
            <button><img src="./assets/images/icon-add-to-cart.svg" alt="Add to Cart"><span>Add to Cart</span></button>
          </div>

          <div class="products__list__item-category red-hat-text-regular">Waffle</div>
          <h2 class="products__list__item-title red-hat-text-semibold">Waffle with Berries</h2>
          <div class="products__list__item-price red-hat-text-bold">6.50</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-creme-brulee-mobile.jpg" srcset="./assets/images/image-creme-brulee-mobile.jpg 769w, ./assets/images/image-creme-brulee-tablet.jpg 992w, ./assets/images/image-creme-brulee-desktop.jpg 1200w" alt="Vanilla Bean Crème Brûlée">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Crème Brûlée</div>
          <h2 class="products__list__item-title">Vanilla Bean Crème Brûlée</h2>
          <div class="products__list__item-price">7.00</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-macaron-mobile.jpg" srcset="./assets/images/image-macaron-mobile.jpg 769w, ./assets/images/image-macaron-tablet.jpg 992w, ./assets/images/image-macaron-desktop.jpg 1200w" alt="Macaron Mix of Five">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Macaron</div>
          <h2 class="products__list__item-title">Macaron Mix of Five</h2>
          <div class="products__list__item-price">8.00</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-tiramisu-mobile.jpg" srcset="./assets/images/image-tiramisu-mobile.jpg 769w, ./assets/images/image-tiramisu-tablet.jpg 992w, ./assets/images/image-tiramisu-desktop.jpg 1200w" alt="Classic Tiramisu">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Tiramisu</div>
          <h2 class="products__list__item-title">Clasic Tiramisu</h2>
          <div class="products__list__item-price">5.50</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-baklava-mobile.jpg" srcset="./assets/images/image-baklava-mobile.jpg 769w, ./assets/images/image-baklava-tablet.jpg 992w, ./assets/images/image-baklava-desktop.jpg 1200w" alt="Pistachio Baklava">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Baklava</div>
          <h2 class="products__list__item-title">Pistachio Baklava</h2>
          <div class="products__list__item-price">4.00</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-meringue-mobile.jpg" srcset="./assets/images/image-meringue-mobile.jpg 769w, ./assets/images/image-meringue-tablet.jpg 992w, ./assets/images/image-meringue-desktop.jpg 1200w" alt="Lemon Meringue Pie">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Pie</div>
          <h2 class="products__list__item-title">Lemon Meringue Pie</h2>
          <div class="products__list__item-price">5.00</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-cake-mobile.jpg" srcset="./assets/images/image-cake-mobile.jpg 769w, ./assets/images/image-cake-tablet.jpg 992w, ./assets/images/image-cake-desktop.jpg 1200w" alt="Red Velvet Cake">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Cake</div>
          <h2 class="products__list__item-title">Red Velvet Cake</h2>
          <div class="products__list__item-price">4.50</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-brownie-mobile.jpg" srcset="./assets/images/image-brownie-mobile.jpg 769w, ./assets/images/image-brownie-tablet.jpg 992w, ./assets/images/image-brownie-desktop.jpg 1200w" alt="Salted Caramel Brownie">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Brownie</div>
          <h2 class="products__list__item-title">Salted Caramel Brownie</h2>
          <div class="products__list__item-price">4.50</div>
        </article>
        <article class="products__list__item">
          <div class="products__list__item-image">
            <img src="./assets/images/image-panna-cotta-mobile.jpg" srcset="./assets/images/image-panna-cotta-mobile.jpg 769w, ./assets/images/image-panna-cotta-tablet.jpg 992w, ./assets/images/image-panna-cotta-desktop.jpg 1200w" alt="Vanilla Panna Cotta">
          </div>
          <button><span></span>Add to Cart</button>
          <div class="products__list__item-category">Panna Cotta</div>
          <h2 class="products__list__item-title">Vanilla Panna Cotta</h2>
          <div class="products__list__item-price">6.50</div>
        </article>
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

