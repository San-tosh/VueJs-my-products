<template>
<div class="row mt-4">
    <div class="col-lg-6">
        <h6>Quote:</h6>
        <textarea class="form-control" v-model="quote" cols="10" rows="5" required></textarea>
        <button @click="addQuote" class="btn btn-primary">Add Quote</button>
    </div>
    </div>
</template>
<script>

import {eventBus} from '../main.js';
export default {
    data:function(){
        return{
            quote:'',
        }
    },
    methods:{
        addQuote(){
            eventBus.$emit('buttonClicked',this.quote);
        }
    }
    
}
</script>
<style scoped>
.col-lg-6{
    margin:auto;
}
.btn{
    display:block;
    margin:auto;
    margin-top:20px;
    font-size: .9rem;
}

</style>