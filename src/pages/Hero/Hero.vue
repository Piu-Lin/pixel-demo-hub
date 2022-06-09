<template>
  <div id="hero-box">
      <img id="hero-jpg" src='/src/assets/Hero/hero.png' alt="">
      
      <div id="loading-title">LOADING...</div>
        <ProgressBar/>
  </div>
</template>
 
<script setup>
import { onMounted,ref } from "vue"; 
import LoadAni from './components/LoadAni.vue'
import ProgressBar from "./components/ProgressBar.vue";
</script>

<style lang="less" scoped>
#hero-box{
    position: absolute;
    top:0;
    bottom:0;
    left:0;
    right: 0;
    #hero-jpg{
        position: absolute;
        width: 100%;
        height: 100%;
        object-fit:cover;
        z-index: 10;
    }
    
    #loading-title{
        position: absolute;
        left:50%;
        top:64%;
        transform:translate(-50%,-50%);
        margin-top: 20px;
        font-size: 18px;
        color:white;
        z-index: 11;
        font-weight: 600;
        // font-family: SimHei;
    }
}
</style>