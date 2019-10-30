<!-- Products in wishlist -->
<template>
    <div class="card my-5">
        <div class="card-body">
            <h5 class="text-center card-title">{{product.title}}</h5>
            <p class="text-center text-muted card-text display-4">${{Number(product.price).toFixed()}}</p>
            <button :disabled="isInWishlist" @click="$emit('add-to-wishlist',product)" class="btn btn-info form-control">
                {{isInWishlist ? 'Added to wishlist': 'Add to Wishlist'}}
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
        background-color: pink;
        border: none;
    }
    button.btn:hover{
        background-color: lightpink;
    }
</style>