<template>
  <div>
    <header>
      <img
        src="./assets/DolceCandles/dolcedeaLogo.jpeg"
        class="logo"
        alt="logo"
        height="100"
      />

      <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
      </nav>
      <button v-on:click="navigateTo('products')">View Products</button>
      {{ cart.length }} in cart
      <button v-on:click="navigateTo('cart')">View Cart</button>
    </header>

    <div v-if="page === 'cart'">
      <h1>Your Cart</h1>
      <div class="products">
        <div v-for="(product, index) in cart" :key="index">
          {{ product.name }}
          <img
            :src="product.image"
            class="pictures"
            alt="candle"
            height="250"
          />
          <div>{{ product.price }}</div>
          <button v-on:click="removeItemFromCart(product)">
            Remove From Cart
          </button>
        </div>
      </div>
    </div>

    <div v-if="page === 'products'">
      <h1>Products</h1>
      <div class="products">
        <div v-for="(product, index) in products" :key="index">
          <img
            :src="product.image"
            class="pictures"
            alt="candle"
            height="250"
          />
          <div>{{ product.name }}</div>
          <div>{{ product.price }}</div>

          <button v-on:click="addItemToCart(product)">Add to cart</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import candle1 from "./assets/DolceCandles/candle1.avif";
import candle2 from "./assets/DolceCandles/candle2.avif";
import candle3 from "./assets/DolceCandles/candle3.avif";
import candle4 from "./assets/DolceCandles/candle4.avif";
import candle5 from "./assets/DolceCandles/candle5.avif";
import candle6 from "./assets/DolceCandles/candle6.avif";
import candle7 from "./assets/DolceCandles/candle7.avif";
import candle8 from "./assets/DolceCandles/candle8.avif";
import candle9 from "./assets/DolceCandles/candle9.avif";
import candle10 from "./assets/DolceCandles/candle10.avif";
import diffuser1 from "./assets/DolceCandles/diffuser1.avif";
import diffuser2 from "./assets/DolceCandles/diffuser2.avif";
import diffuser3 from "./assets/DolceCandles/diffuser3.avif";
import diffuser4 from "./assets/DolceCandles/diffuser4.jpeg";
import diffuser5 from "./assets/DolceCandles/diffuser5.avif";
// import dolcedeaLogo from "./assets/DolceCandles/dolcedeaLogo.jpeg";
export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: [],
      products: [
        { name: "Brennan Michael", price: "N15,000", image: candle1 },
        {
          name: "Smokey Wood",
          price: "N21,000",
          image: candle2,
        },
        {
          name: "Scented Candle",
          price: "N10,000",
          image: candle3,
        },
        {
          name: "SEV",
          price: "N10,000",
          image: candle4,
        },
        {
          name: "Coziness",
          price: "N10,000",
          image: candle5,
        },
        {
          name: "Tea Lights",
          price: "N10,000/12",
          image: candle6,
        },
        {
          name: "La Femme Fatale",
          price: "N25,000",
          image: candle7,
        },
        {
          name: "La Nuit plus belle",
          price: "N10,000",
          image: candle8,
        },
        {
          name: "Scented Candle",
          price: "N10,000",
          image: candle9,
        },
        {
          name: "Scented Candle Set",
          price: "N10,000",
          image: candle10,
        },
        {
          name: "Diffuser",
          price: "N10,000",
          image: diffuser1,
        },
        {
          name: "Diffuser",
          price: "N10,000",
          image: diffuser2,
        },
        {
          name: "Diffuser",
          price: "N10,000",
          image: diffuser3,
        },
        {
          name: "Diffuser",
          price: "N10,000",
          image: diffuser4,
        },
        {
          name: "Diffuser",
          price: "N10,000",
          image: diffuser5,
        },
      ],
      summary: "lorem ipsum",
    };
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
      console.log(this.cart);
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product));
    },
    navigateTo(page) {
      this.page = page;
    },
  },

  components: {},
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
  font-family: "Roboto", sans-serif;
}
</style>
<style scoped>
.products {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  justify-items: center;
  grid-gap: 20px;
}
.pictures {
  border-radius: 10px;
  width: 200px;
}
h1 {
  text-align: center;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 40px;
  background-color: #f5f5f5;
  text-align: right;
  padding: 10px;
  /* margin: 20px; */
  font-size: 20px;
  box-shadow: 2px 2px 5px #999;
}
header a {
  text-decoration: none;
  color: #000;
  margin: 0 20px;
}
/* .logo{
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin: 0 20px;
} */
</style>
