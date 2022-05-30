<template>
    虚假链接:
    
</template>

<script setup>
import {onMounted,ref} from "vue"
onMounted(()=>{
    text()
})
let timer

const emit = defineEmits(["trigger"])

const text=()=>{
    timer=setTimeout(() => {
        text2()
      }, 8000);
}
const text2=()=>{
    clearTimeout(timer);
    console.log("定时结束")
    emit("trigger",true)
}

</script>

<style>

</style>