<template>
  <div id="hero-box">
      <img id="hero-jpg" src='/src/assets/Hero/hero.jpg' alt="">
      <div id="loading-ani">
          <LoadAni/>
      </div>
      <div id="loading-title">资源加载中</div>
  </div>
</template>

<script setup>
import { onMounted,ref } from "vue";
import LoadAni from './components/LoadAni.vue'
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
        z-index: -1;
    }
    #loading-ani{
        position: absolute;
        left:50%;
        top:40%;
        transform:translate(-50%,-50%);
    }
    #loading-title{
        position: absolute;
        left:50%;
        top:60%;
        transform:translate(-50%,-50%);
        margin-top: 20px;
        font-size: 24px;
        color:wheat;
        opacity: 0.8;
    }
}
</style>