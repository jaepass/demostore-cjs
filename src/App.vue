<template>
  <div class="container mt-4">
    <header>
      <div class="logo">
        <img width="150px" src="@/assets/logo.png" alt="Tribal Logo">
      </div>
      
      <nav>
        <img width="30px" src="@/assets/fav-icon.svg" alt="Tribal Logo">
        <img width="30px" src="@/assets/shopcart-icon.svg" alt="Tribal Logo">
      </nav>

    </header>


    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <!-- :key is for Vue to keep track of items -->
          <div class="col-md-6" v-for="product in products" :key="product.id" >
            <product :isInWishlist="isInWishlist(product)"
                      v-on:add-to-wishlist="addToWishlist(product)"
                      :product="product"
            ></product>
              
          </div>
        </div>
      </div>
      <!-- Wishlist modal -->
      <div class="col-md-5 my-5">
        <wishlist v-on:pay="pay()" v-on:remove-from-wishlist="removeFromWishlist($event)" :items="wishlist"></wishlist>
      </div>
    </div>
  </div>
</template>

<script>
// Importing in components and data
import products from "@/products.json";
import Product from "@/components/Product.vue";
import Wishlist from "@/components/Wishlist.vue";

// Initialize store with public key
// const myStore = new Commerce('pk_168757b95ff55c066b59b9e93c48a2b0e7bc1b97c798b', true);

export default {
  name: "app",
  components: {
    Product,
    Wishlist, 
  },
  data() {
    return {
      products,
      wishlist: [],

    };
  },
  //   mounted() { 
  //     //When element is mounted, look up data with store instance key
  //     myStore.Products.list(function(resp){
  //         console.log(resp);
  //         this.products = resp.data
  //         },
  //       function(error){
  //         //Error handler
  //         }
  //       );

  // },
  methods: {
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
}

header {
  
  display: flex;
}

nav{
  
  position: relative;
  align-items: right;
  display: flex;
}
</style>