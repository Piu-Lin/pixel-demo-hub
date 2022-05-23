<template>
    <div id="message-demo">
        <input v-model="messageText" id="input-message" />
        <div @click="snedMessage" id="send-message">发送请求</div>
        <div id="restore" >还原位置</div>
    </div>
    
</template>

<script setup>
import { ref } from "@vue/reactivity"
let messageText=ref("")
function snedMessage() {
    console.log("开始传输"+messageText.value)
    window.connection.emitUIInteraction(messageText.value)
    console.log("传输结束")
}
</script>

<style lang="less" scoped>
#message-demo{
    position: absolute;
    color:white;
    z-index: 1;
    #input-message{
        height: 20px;
        margin-top: 30px;
    };
    #send-message{
        width: 100%;
        height: 40px;
        background-color: aqua;
        cursor: pointer;
        border-radius:8px;
        text-align: center;
        line-height:40px;
    }
    #restore{
        width: 100%;
        height: 40px;
        background-color:antiquewhite;
        cursor: pointer;
        border-radius:8px;
        text-align: center;
        line-height:40px;
    }
}

</style>
