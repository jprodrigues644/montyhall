<template>
    <div class = " door-area">
         <div class ="door-frame" :class="{ selected : selected  && !open}" >
            <Gift v-if="open && hasGift" />
        </div>
        <div class = "door" @click ="selected = !selected" :class="{open}" >
            <div class = "number" :class="{selected}"> {{ number }}</div>

            <div class = "door-knob"  @click.stop ="open = true" :class="{selected}">

            </div>
        </div>
        
    </div>
</template>

<script>
   import Gift from './giftComponent'
   export default  {
        name : 'DoorComponent' ,
        components : {Gift} ,
        props : {
            number : {}, 
            hasGift : {type:  Boolean}
        },

        data : function () {
            return {
                open : false,
                selected :false
            }
        }
   }

</script>

<style>
    :root {
        --door-border : 5px solid rgb(109, 78, 78) ;
        --selected-border : 5px solid rgb(170, 253, 15);
    }
    .door-area {
        position : relative;
        width : 200px;
        height : 320px;
        border-bottom : 10px solid rgb(48, 25, 25);
        margin-bottom : 20px;
        font-size : 3em;

        display : flex;
        justify-content : center;

    }

    .door-frame {
        position : absolute;
        height : 310px;
        width:180px ;
        border-left : var(--door-border);
        border-right : var(--door-border);
        border-top : var(--door-border);
        display : flex;
        justify-content: center ;
        align-items : flex-end ;
    }

    .door {
        position : absolute ;
        top : 5px;
        height : 305px;
        width:175px ;
        background-color:rgb(197, 131, 107);
        display : flex;
        flex-direction:column;
        align-items: center ;
        padding: 20px;

    }

    .door-knob {
        height :20px;
        width: 20px;
        border-radius:10px;
        background-color: rgb(53, 13, 13);
        align-self: flex-end;
        margin-top : 50px;

    }
    .door-frame.selected {
        border-left: var(--selected-border);
        border-top: var(--selected-border);
        border-right:var(--selected-border);
    }

    .door-knob.selected{
       
        background-color:  rgb(170, 253, 15);
    }

    .number.selected{
        color:rgb(170, 253, 15);
    }

    .door.open
    {
        background-color: rgb(24, 23, 23);
    }
    .door.open .door-knob{
        display :none;
    }

    .door.open .number {
        display :none;
    }

</style>