<script setup>
import {useMealStore} from '../../store/Meals.js';
import meal from '../meals/meal.vue';
import message2 from './message2.vue';


const meals=useMealStore();
</script>

<template>

    <div class="page">
        <!-- 已选项目页 -->
        <div class="part">

            <!-- 页面抬头 -->
            <div class="title">
                <div class="can">餐品详情</div>
                <div class="delAll" @click="meals.toEmpty">
                    <i class="ri-delete-bin-5-fill"></i>
                    <div>清空购物车</div>
                </div>
            </div>

            <!-- 已选内容 -->
            
            <div class="cont">
                <template v-if="meals.getSum==0">
                    <div class="noresult" >还未添加商品到购物车哦！</div>
                </template>
                <meal v-for="meal in meals.getChosed" :item="meal">
                    <message2 :item="meal"></message2>
                </meal>
            </div>
        </div>
    </div>
</template>

<style scoped>

.page{
    height:100vh;
    width:100vw;
    position:absolute;
    top:0;
    left:0;
    background-color:rgb(138, 134, 134,50%);

}
.part{
    height:750rem;
    width:100vw;
    position:absolute;
    bottom: 0;
    background-color: white;
    border-radius:20rem 20rem 0 0;
}
.title{
    height:45rem;
    position: relative;
}
.can{
    position:absolute;
    bottom:5rem;
    left:20rem;
    font-size: 17rem;
    font-weight: bolder;

}
.delAll{
    position:absolute;
    width:90rem;
    bottom: 5rem;
    right:20rem;
    font-size:14rem;
    display:flex;
    justify-content: space-between;
    align-items: center;
    color:rgb(151, 151, 151);

}
.noresult{
    /* background-color: aqua; */
    height: 60rem;
    width:300rem;
    font-size: 15rem;
    padding:30rem 20rem;
    color:gray;
}
.cont{
    height:700rem;
    overflow: auto;
    padding-bottom: 80rem;
}
</style>