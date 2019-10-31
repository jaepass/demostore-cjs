<!-- Products in wishlist -->
<template>
    <div class="card my-5">
        <div class="card-body">
            <img :src="product.media.source" :alt="product.name" />
            <h4 class="title text-center card-title display-5">{{product.name}}</h4>
            <p class="description text-center card-title display-5">{{product.description}}</p>
            <p class="text-center text-muted card-text display-5">{{product.price.formatted_with_symbol}}</p>
            <button :disabled="isInWishlist" @click="$emit('add-to-wishlist',product)" class="btn btn-info form-control"><i class="fas fa-heart"></i>{{isInWishlist ? 'Added to wishlist': 'Add to Wishlist'}}
            </button>
        </div>
    </div>
</template>

<script>
export default{
    props: ['product','isInWishlist']
}
</script>

<style>
    button.btn{
        background-color: transparent;
        text-decoration: underline;
        border: none;
        color: rgb(60, 60, 60);
    }
    button.btn:hover{
        text-decoration: none;
        background-color: transparent;
        color: rgb(60, 60, 60);
    }
</style>