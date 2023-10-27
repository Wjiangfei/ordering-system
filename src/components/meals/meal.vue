<script setup>
import { defineProps } from 'vue';


const props=defineProps(["item"]);
</script>

<template>
    <div class="meal">
        <div class="pic">
             <img :src="props.item.img">
        </div>
        <slot></slot>
        
        
    </div>
    
</template>

<style scoped>
.meal{
    height:150rem;
    margin:0 7rem;
    /* background-color: antiquewhite; */
    overflow: hidden;
    /* border-bottom:rgb(233, 230, 230) 0.5rem solid; */
    border-bottom:rgb(241, 241, 241) 0.5rem solid;
}
.pic{
    float: left;
    width:140rem;
    height:140rem;
    margin:auto 0;
}
img{
    width:140rem;
    height:140rem;
}

</style>
