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
}, 25)
function sleep (time) {
    return new Promise((resolve) => setTimeout(resolve, time));
}
onBeforeUnmount( async()=>{
    while(1){
        await sleep(1000)
    }
    rate.value=100
})

</script>

<style lang="less" scoped>
#progress{
    position: absolute;
    width: 70%;
    height: 5%;
    left: 50%;
    bottom: 15%;
    transform:translate(-50%,-50%);
    z-index: 11;
    border-radius: 8px;
    overflow: hidden;
    #rate{
        position: relative;
        height:100%;
        left: 0px;
        width: 50%;
        background-color:#ff1d5e;
    }
}
</style>