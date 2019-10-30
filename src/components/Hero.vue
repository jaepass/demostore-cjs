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
            <div class="hero-bg"></div>
        </header>

        
        <img width="675px" src="@/assets/hero-img.jpg" class="hero-img" alt="hero image">
        
    </div>
</template>


<script>
   export default{

   }
</script>

<style>

.hero-wrapper {

    position: relative;
}

header{
    display: flex;
    z-index: 999
}

nav{
    z-index: 999;
    padding: 20px 20px 0 0;
}

.hero-img{
    position: relative;
    z-index: 1;
    display: flex;
    left: 50%;
    top: 50%;
    transform: translateX(-50%);
}

.hero-bg {
    position: absolute;
    height: 80vh;
    width: 50vw;
    background-color: #DBA28B;
    display: flex;
    right: 0;
}

</style>