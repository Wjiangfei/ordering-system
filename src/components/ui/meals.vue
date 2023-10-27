<script setup>
import meal from '../meals/meal.vue';
import {useMealStore} from '../../store/Meals.js';
import Message from '../meals/message.vue';

const meals=useMealStore();


</script>

<template>
    <div class="meals">

        <meal v-for="meal in meals.findTaget"  :item="meal">
            <message :item=meal></message>
        </meal>

        <template v-if="meals.findTaget.length==0">
            <div class="noresult" >没有这种东西哦！</div>
        </template>

    </div>
    

    
    
</template>

<style scoped>
.noresult{
    /* background-color: aqua; */
    height: 30rem;
    width:200rem;
    font-size: 12rem;
    padding:10rem 40rem;
    color:gray;
}
.meals{
    height:100vh;
    padding: 50rem 0 60rem 0;
    width:100vw;
    overflow:auto;
}

</style>