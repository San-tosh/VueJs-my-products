<template>
<div class="row mt-5">
    <div class="col-lg-12 col-xs-12">
        <h4>Quotes Added</h4>
            <div class="progress-bar" >
                <div class="progress" :style="{width:width+'%'}">
                   <font>{{quoteCounter}}/10</font>
                </div>
            </div>
    </div>
    </div>
</template>
<script>
import {eventBus} from '../main.js';
export default {
    data:function(){
        return{
            width:10,
            quoteCounter:1
        }
    },
    created(){
        eventBus.$on('itemDeleted',(a)=>{
            this.width-=10;    
                --this.quoteCounter;
        });
            eventBus.$on('buttonClicked',(a)=>{
                if(this.quoteCounter<10){
                this.width+=10;    
                ++this.quoteCounter;
                }
            });
    }
}
</script>
<style scoped>
.progress-bar{
    width:100%;
    background-color:#ccc;
    border-radius:5px;
    height: 20px;
    
}
.progress{
    position: relative;
    background-color:#007bff;
    height:20px;
    width:10;
    border-top-right-radius: 0;
    border-bottom-right-radius: 0;
    transition:background-color 1000ms ease-in-out,
                width 1000ms ease-in-out;
}
h4{
    font-weight: bolder;
}
font{
    margin:auto;
    font-weight:  bold;
}
</style>
