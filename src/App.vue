<template>
<!-- <MessageDemo/> -->
<!-- <Connect/> -->
<Hero v-show="!LoadComplete"/>
<FakeConnet  v-show="LoadComplete"  @trigger="trigger"/>

</template>
<script setup>
import {ref} from "vue"
import Connect from './connect.vue'
import MessageDemo from './components/messageDemo.vue'
import Home from './pages/Home.vue'
import Hero from './pages/Hero/Hero.vue'
import FakeConnet from './components/FakeConnet.vue';
import VueRouter from 'vue-router'
/** 资源加载是否完成 */
let LoadComplete = ref(false)
const trigger=()=>{
    console.log("收到扳机")
    LoadComplete.value=true
}
</script>
<style>
body {
    width : 100vw;
    height : 100vh;
    margin: 0;
}
</style>

