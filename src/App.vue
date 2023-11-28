<script setup>
import meals from './components/ui/meals.vue';
import search from './components/ui/search.vue';
import cartBag from './components/ui/cart-bag.vue';
import added from './components/payUI/added.vue';
import pay from './components/payUI/pay.vue';
import { useMealStore } from './store/Meals';


const usemeal=useMealStore();

</script>

<template>
    <div class="home">
        <search style="z-index:0;"></search>
        <meals style="z-index:0;"></meals>
        <added v-show="usemeal.ifcheck"></added>
        <pay v-show="usemeal.ifpay" style="z-index:2;"></pay>
        <cartBag></cartBag>
        
        
    </div>

</template>
<style scoped>
.home{
    width:390rem;
    margin:0 auto;
    /* border:1rem rgb(197, 197, 197) solid; */
    position:relative;
    overflow: hidden;
}

</style>

