<template>
<Connect @trigger="trigger"/>
<Hero v-if="!LoadComplete"/>
<!-- <FakeConnet @trigger="trigger"/> -->
<Interaction/> 
</template>
<script setup>
import {ref} from "vue"
import Connect from './connect.vue'
import MessageDemo from './components/messageDemo.vue'
import Hero from './pages/Hero/Hero.vue'
import FakeConnet from './components/FakeConnet.vue'
import Interaction from './pages/Interaction/Interaction.vue'

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
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}

</style>

