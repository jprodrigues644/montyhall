<template>
    <div class="gift">
        <div class=" gift-top"></div>
        <div class = "lace-1"></div>
         <div class = "lace-2"></div>
        <div class = "gift-body"></div>
        <div class = "gift-bottom"></div>
        


    </div>
</template>

<script>

    export default {

    }
</script>

<style>
    .gift {
        position : relative ; 
        display : flex ;
        flex-direction : column ;
        align-items : center ;
        z-index :10 ;
    }
    
    .gift-top {
            width: 120px ;
            height : 20px;
            background-color : rgb(7, 161, 2);
        }
    .gift-body {
            width : 100px;
            height : 80px ;
            background-color : rgb(60, 85, 12) ;
    }


    .lace-1 {
            position : absolute;
            width : 10px;
            height : 100px ;
            background-color : red;
            }

    .lace-2 {
             position : absolute;
            top : 50px;
            width : 100px;
            height : 10px ;
            background-color : red;
    }
</style>