<template>
  <div>
    <header>
      <button v-on:click="navigateTo('products')">View Products</button>
      {{ cart.length }} in cart
      <button v-on:click="navigateTo('cart')">View Cart</button>
    </header>

    <div v-if="page === 'cart'">
      <h1>Your Cart</h1>
      <div class="products">
        <div v-for="(product, index) in cart" :key="index">
          <h4>{{ product.name }}</h4>
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
          <div>
            <button v-on:click="addItemToCart(product)">+</button>
            <button v-on:click="removeItemFromCart(product)">-</button>
          </div>
          <div>
            <button v-on:click="navigateTo('checkout')" class="checkout-button">
              Checkout
            </button>
          </div>
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
          <div class="price">{{ product.price }}</div>

          <button v-on:click="addItemToCart(product)">Add to cart</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import Products from "./components/ProductPage.vue";
import candle1 from "./assets/DolceCandles/candle1.jpeg";
import candle2 from "./assets/DolceCandles/candle2.jpeg";
import candle3 from "./assets/DolceCandles/candle3.jpeg";
import candle4 from "./assets/DolceCandles/candle4.jpeg";
import candle5 from "./assets/DolceCandles/candle5.jpeg";
import candle6 from "./assets/DolceCandles/candle6.jpeg";
import candle7 from "./assets/DolceCandles/candle7.jpeg";
import candle8 from "./assets/DolceCandles/candle8.jpeg";
import candle9 from "./assets/DolceCandles/candle9.jpeg";
import candle10 from "./assets/DolceCandles/candle10.jpeg";
import diffuser1 from "./assets/DolceCandles/diffuser1.jpeg";
import diffuser2 from "./assets/DolceCandles/diffuser2.jpeg";
import diffuser3 from "./assets/DolceCandles/diffuser3.jpeg";
import diffuser4 from "./assets/DolceCandles/diffuser4.jpeg";
import diffuser5 from "./assets/DolceCandles/diffuser5.jpeg";

export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: [],
      products: [
        { name: "Brennan Michael", price: "N15,000", image: candle1, },
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
      this.cart.splice(this.cart.indexOf(product), 1);
    },
    navigateTo(page) {
      this.page = page;
    },
    navigateToProducts() {
      this.page = "products";
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
.products .price {
  font-size: 15px;
}
.products button {
  background-color: #f5f5f5;
  border: 1px solid #000;
  border-radius: 8px;
  padding: 5px;
  margin: 5px;
  font-size: 15px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.products button:hover {
  background-color: #000;
  color: #fff;
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
  justify-content: right;
  align-items: center;
  height: 40px;
  background-color: #f5f5f5;
  padding: 10px;
  font-size: 20px;
  box-shadow: 2px 2px 5px #999;
}
header button {
  background-color: #f5f5f5;
  border: 1px solid #000;
  border-radius: 8px;
  padding: 5px;
  margin: 5px;
  font-size: 15px;
  cursor: pointer;
  transition: all 0.3s ease;
}
header button:hover {
  background-color: #000;
  color: #fff;
}

@media (max-width: 768px) {
  header {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 40px;
    background-color: #f5f5f5;
    padding: 5px;
    font-size: 15px;
    box-shadow: 2px 2px 5px #999;
  }
  .products {
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 1px;
  }
  .products .price {
    font-size: 12px;
  }
  .products button {
    background-color: #f5f5f5;
    border: 1px solid #000;
    border-radius: 5px;
    padding: 3px;
    margin: 3px;
    font-size: 12px;
  }
  .pictures {
    border-radius: 5px;
    width: 130px;
    height: 100px;
  }

}
</style>
