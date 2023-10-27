<script setup>
import { useMealStore } from '../../store/Meals';
import paymeal from './paymeal.vue';

const meals=useMealStore();

</script>

<template>
    <div class="pay">
        <!-- 返回键 -->
        <div class="close" @click="meals.payToggle"><i class="ri-close-line"></i></div>
        <!-- 小票 -->
        <div class="receipt">
            <!-- 标题 -->
            <div class="title">餐品详情</div>
            <!-- 内容 -->
            <div class="content">
                <paymeal v-for="meal in meals.getChosed" :item=meal></paymeal>
            </div>
            <!-- 合计 -->
            <!-- <div class="res">
                合计 
                <div class="price">{{ meals.priceSum }}</div>
            </div> -->
        </div>
    </div>
</template>

<style scoped>
.pay{
    height:100vh;
    width:100vw;
    background-color: rgb(240, 240, 240);
    position:absolute;
    top:0;
    left:0;
}
.close{
    width:25rem;
    height:25rem;
    font-size:25rem;
    font-weight: bold;
    margin:10rem 0 10rem 5rem;
}
.receipt{
    width:380rem;
    background-color: white;
    margin:0 auto;
    border-radius: 25rem;
}
.title{
    height:60rem;
    width:340rem;
    margin:20rem auto 0 auto;
    padding-top:20rem;
    font-size:18rem;
    font-weight: bold;
    line-height: 30rem;
    

}
.content{
    margin:0 auto;
    width:340rem;
    border-bottom: 0.5px solid rgb(207, 207, 207);
    border-top: 0.5px solid rgb(207, 207, 207);
}
</style>