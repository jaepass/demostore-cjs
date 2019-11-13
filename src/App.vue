<template>
  <div class="storefront">
    
  <!-- Hero component contains header -->
  <store-hero></store-hero>

    <div class="container mx-auto px-4">
      <div class="flex mb-4">
        <div class="row" id="shop">
          <!-- :key is for Vue to keep track of items with ids -->
          <div class="col-sm-4" v-for="product in products" :key="product.id" >
            <product :isInCart="isInCart(product)"
                      v-on:add-to-cart="addToCart(product)"
                      :isInWishlist="isInWishlist(product)"
                      v-on:add-to-wishlist="addToWishlist(product)"
                      :product="product"
            ></product>
              
          </div>
        </div>
      </div>

      <div class="cart-wishlist">
        <!-- Cart modal -->
        <div class="col-md-5 my-5" id="shopping-cart">
          <cart v-on:remove-from-cart="removeFromCart($event)" :items="cart"></cart>
        </div>
        <!-- Wishlist modal -->
        <div class="col-md-5 my-5" id="wishlist">
          <wishlist v-on:remove-from-wishlist="removeFromWishlist($event)" :items="wishlist"></wishlist>
        </div>
    </div><!-- END Cart/Wishlist Container -->

    </div><!-- End of Individual Product cards -->

     <!-- Footer -->
    <store-footer></store-footer>

  </div>
</template>



<script>

//Import Commerce.js products
import Commerce from '@chec.io/commerce';
// Importing mock data
import products from "@/products.json";
// Importing components
import Product from "@/components/Product.vue";
import Cart from "@/components/Cart.vue";
import Wishlist from "@/components/Wishlist.vue";
import Hero from "@/components/Hero.vue";
import Footer from "@/components/Footer.vue";


// Initialize store with public key, store key in variable myStore
const myStore = new Commerce('pk_168757b95ff55c066b59b9e93c48a2b0e7bc1b97c798b', true);

export default {
  name: "app",
  components: {
    // 'store-header': Header,
    'store-hero': Hero,
    'store-footer': Footer,
    Product,
    Cart,
    Wishlist, 
  },
  data() {
    return {
      products,
      //loading,
      cart: [],
      wishlist: []
    };
  },


//When element is mounted, look up data with store instance key
  mounted() {
    //List all products from chec 
    myStore.products.list()
      .then((resp) => {
        //console.log(resp);
        this.products = resp.data
        this.loading = false
      })
      .catch((error) => {
                alert(error);
            });  
  },

  //Declare action methods on object
  methods: {
    // Cart methods
    addToCart(product){
      this.cart.push(product);
    },
    isInCart(product){
      const item = this.cart.find(item => item.id === product.id);
      if(item){
        return true;
      }
      return false;
    },
    removeFromCart(product){
      this.cart = this.cart.filter(item => item.id !== product.id);
    },
    // Wishlist methods
    addToWishlist(product) {
      this.wishlist.push(product);
    },
    isInWishlist(product) {
      const item = this.wishlist.find(item => item.id === product.id);
      if (item) {
        return true;
      }
      return false;
    },
    removeFromWishlist(product) {
      this.wishlist = this.wishlist.filter(item => item.id !== product.id);
    } 
  }
};
</script>

<style>
body {
  background-color: #ffffff;
  font-family: 'Lato', sans-serif;
}

h1, h2, h3, h4{
  text-transform: uppercase;
}

.cart-wishlist{
  display: flex;
  justify-content: space-between;
}


</style>