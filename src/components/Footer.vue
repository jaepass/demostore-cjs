<template>
    <footer>
    <div class="footer-logo">
        <img width="150px" src="@/assets/logo.png" alt="Tribal Logo">
    </div>
    <div class="footer-txt">
        <p>Demo Store utilizing Commerce.js API</p>
        <p>Vue.js integration</p>
    </div>
    
    <nav class="ml-auto">
    
    </nav>
</footer>
</template>


<script>
   export default{

   }
</script>

<style>
    footer{
        height: 50vh;
        width: 70vw;
        background-color: black;
    }

    .footer-logo{
        position: absolute;
        right: 45px;
        padding-top: 20px;
    }

    .footer-txt{
        color: white;
        letter-spacing: 2.75px;
        padding: 40px;
    }
</style>