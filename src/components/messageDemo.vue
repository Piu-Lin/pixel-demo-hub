<template>
    <div id="message-demo">
        <input v-model="messageText" id="input-message" />
        <div @click="snedCustomMessage" id="send-message">发送请求</div>
        <div @click="snedAssignMessage(day)" class="bott">白天</div>
        <div @click="snedAssignMessage(night)" class="bott">黑夜</div>
        <div @click="snedAssignMessage(res)" class="bott">还原位置</div>
        <div @click="snedAssignMessage(character)" class="bott">人物</div>
        <div @click="snedAssignMessage(water)" class="bott">水位</div>
        <div @click="snedAssignMessage(view)" class="bott">显示模式</div>
    </div>
</template>

<script setup>
import { ref } from "@vue/reactivity"
let messageText=ref("")
const day='{"eventname": "Event_day"}'
const night='{"eventname": "Event_night"}'
const res='{"eventname": "Event_reset_default_view"}'
const character ='{"eventname": "Event_character_tag"}'
const water ='{"eventname": "Event_water_level"}'
const view ='{"eventname": "Event_view_mode"}'
function snedCustomMessage() {
    console.log("开始传输"+messageText.value)
    window.connection.emitUIInteraction(messageText.value)
    console.log("传输结束")
}

function snedAssignMessage(assignMessage) {
    console.log("开始传输"+assignMessage)
    window.connection.emitUIInteraction(assignMessage)
    console.log("传输结束")
}

</script>



<style lang="less" scoped>
#message-demo{
    position: absolute;
    color:white;
    z-index: 1;
    right:0px;
    #input-message{
        height: 20px;
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
    .bott{
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
