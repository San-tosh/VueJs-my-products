<template>
<div class="row mt-4">
    <div class="col-lg-12 col-xs-12">
        <ul >
            <li v-for="(item,i) in items" @click="quoteDelete(i)">
                {{item}}
            </li>
        </ul>
    </div>
    </div>
</template>
<script>
import {eventBus} from '../main.js';
export default {
    data:function(){
        return{
            items:['Self Consciousness']
        }
    },
    methods:{
        quoteDelete(i){
            this.items.splice(i,1);
             if(this.items.length>=0){
            eventBus.$emit('itemDeleted','');
             }
        }
    },
    created(){
            eventBus.$on('buttonClicked',(a)=>{
                if(this.items.length<10){
           this.items.unshift(a);
                }
            });
        }
}
</script>
<style scoped>
li{
    border: 1px solid #ccc;
    display: block;
    width: 23%;
    float: left;
    padding: 20px;
    margin: 3px -1px 12px 19px;
    border-radius:4px;
    font-family: 'Arizonia', cursive;
    font-size:.1.3rem;
   
}
li:hover{
    background-color:rgb(247, 208, 215);
}
ul{
    padding:0;
    margin:0;
}

</style>
