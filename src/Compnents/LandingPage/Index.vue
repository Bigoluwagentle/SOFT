<script setup>
import data from "./Data.json";
import Header from "../Header/Header.vue";

// Example addToCart function
function addToCart(item) {
  console.log("Added to cart:", item);
}
</script>

<template>
  <Header />
  <span>New Arrivals</span>
  <div class="products">
    <div
      v-for="item in data"
      :key="item.id"
      class="product-card"
    >
      <nav>
        <video 
          :src="item.video" 
          
          autoplay
          muted 
          loop 
          class="product-video"
        ></video>
      </nav>
      <span>{{ item.category }}</span>
      <p>₦{{ item.price }}</p>
      <button @click="addToCart(item)">Add to Cart</button>
    </div>
  </div>
</template>

<style scoped>
span{
    display: block;
    text-align: center;
    margin-top: 100px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 50px;
}
.products{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 150px;
}
.product-video {
  width: 70%;
  border-radius: 10px;
}
video{
    width: 100%;
}
@media screen and (max-width: 750px){
    .products{
        flex-direction: column;
        margin-top: 150px;
        align-items: center;
        justify-content: center;
    }
    .product-video {
        width: 80%;
    }
}
</style>
