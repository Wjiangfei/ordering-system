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
    <div>
        <search style="z-index:0;"></search>
        <meals style="z-index:0;"></meals>
        <added v-show="usemeal.ifcheck" style="z-index:1;"></added>
        <pay v-show="usemeal.ifpay" style="z-index:2;"></pay>
        <cartBag style="z-index:3;"></cartBag>
        
    </div>

</template>
<style scoped>


</style>

