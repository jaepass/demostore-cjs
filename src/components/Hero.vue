<template>
    <div class="hero-wrapper">
        <header>
            
            <div class="logo" >
                <img width="175px" src="@/assets/logo.png" alt="Tribal Logo">
            </div>
            
            <nav class="ml-auto">
                <a href=""><img width="28px" src="@/assets/fav-icon.svg" alt="Tribal Logo"></a>
                <a href=""><img width="28px" src="@/assets/shopcart-icon.svg" alt="Tribal Logo"></a>
            </nav>
            <div class="hero-bg"></div>
        </header>

        <img width="675px" src="@/assets/hero-img.jpg" class="hero-img" alt="hero image">

        <div class="hero-text">
            <h1>Street</h1>
            <h1>Runway</h1>
            <h1>Chic</h1>
        </div>

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
    padding: 30px 30px 0 0;
}

nav a img {
    margin-left: 25px;
}

.logo{
    padding: 30px 0 0 30px;
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

.hero-text{
    position: absolute;
    border: 1px solid blue;
    top: 50%;
}

</style>