<template>
    <div class="hero-wrapper">
        <header>
        <div class="logo">
            <img width="150px" src="@/assets/logo.png" alt="Tribal Logo">
        </div>
        
        <nav class="ml-auto">
            <img width="30px" src="@/assets/fav-icon.svg" alt="Tribal Logo">
            <img width="30px" src="@/assets/shopcart-icon.svg" alt="Tribal Logo">
        </nav>
        </header>

        <img width="675px" src="@/assets/hero-img.jpg" class="hero-img" alt="hero image">
        <div class="hero-bg"></div>
    </div>
</template>


<script>
   export default{

   }
</script>

<style>

header{
    display: flex;
}

.hero-img{
    position: absolute;
    z-index: 999;
    align-content: center;
    margin: 0 auto;
}

.hero-bg {
    position: relative;
    height: 80vh;
    width: 800px;
    background-color: #DBA28B;
}

</style>