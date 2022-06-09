<template>
       <div id="progress">
            <div :style="{width:rate+'%'}" id="rate"></div>
        </div>
</template>

<script setup>
import{ref,onBeforeUnmount,onUnmounted} from "vue"
let rate= ref(0)
let timer
timer = setInterval(() => {
    rate.value+=0.1
    if(rate.value>=100){
        clearInterval(timer)
    }   
}, 30)

</script>

<style lang="less" scoped>
#progress{
    position: absolute;
    width: 70%;
    height: 1.5%;
    left: 50%;
    bottom: 25%;
    transform:translate(-50%,-50%);
    z-index: 11;
    border-radius: 8px;
    overflow: hidden;
    border: .1px solid white;
    background-color:rgba(255, 255, 255, 0.5);

    #rate{
        position: relative;
        height:100%;
        left: 0px;
        width: 50%;
        background-color:#ffffff;
    }
}
</style>