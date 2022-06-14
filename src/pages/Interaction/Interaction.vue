<template>
<div id="bottomBox">
  <div @click="switchDayNight" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/night.png" alt=""/>
    <div class="modeContent">夜间模式</div>
    <img  v-show="state.isNight" class="bottonBg" src="/src/assets/Interaction/bottom1.png"/>
    <img  v-show="!state.isNight" class="bottonBg" src="/src/assets/Interaction/bottom2.png"/>
  </div>
  <div @click="switchRain" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/rain.png" alt=""/>
    <div class="modeContent">雨天模式</div>
    <img  v-show="state.isRain" class="bottonBg" src="/src/assets/Interaction/bottom1.png"/>
    <img  v-show="!state.isRain" class="bottonBg" src="/src/assets/Interaction/bottom2.png"/>
  </div>
  <div @click="snedAssignMessage(res)" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/initLoaction.png" alt=""/>
    <div class="modeContent">位置重置</div>
    <img class="bottonBg" src="/src/assets/Interaction/bottom2.png"/>
  </div>
  <div @click="snedAssignMessage(play)" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/play.png" alt=""/>
    <div class="modeContent">场景漫游</div>
    <img class="bottonBg" src="/src/assets/Interaction/bottom2.png"/>
  </div>
</div>
</template>

<script setup>
import {ref,reactive } from 'vue'
const day='{"eventname": "Event_day"}'
const night='{"eventname": "Event_night"}'
const res='{"eventname": "Event_reset_default_view"}'
const play='{"eventname": "Event_play_movie"}'
const sunny='{"eventname": "Event_sunny_day"}'
const rainy='{"eventname": "Event_rainny_day"}'
let state = reactive({
  isNight:false,
  isRain:false,
})

const switchDayNight=()=>{
  state.isNight?snedAssignMessage(day):snedAssignMessage(night)
  state.isNight=!state.isNight
}
const switchRain =()=>{
  state.isRain?snedAssignMessage(sunny):snedAssignMessage(rainy)
  state.isRain=!state.isRain
}
function snedAssignMessage(assignMessage) {
    console.log("开始传输"+assignMessage)
    window.connection.emitUIInteraction(assignMessage)
    console.log("传输结束")
}
</script>

<style lang="less" scoped>
#bottomBox{
    display: flex;
    position:absolute; 
    bottom:44px;
    width:100%;
    justify-content:center;
    z-index: 2;
    .Mode{
      display: flex;
      position: relative;
      margin: 0px 10px;
      align-items: center;
      cursor: pointer;
      padding:12px;
      justify-content: space-evenly;
      .Icon{
        width: 25px;
        height: 25px;
        z-index: 3;
        opacity: .8;
      }
      .modeContent{
        font-size:12px;
        color: black;
        z-index: 3;
        margin-left: 4px;
        opacity: .8;

      }
      .bottonBg{
        position: absolute;
        left: 0px;
        width: 100%;
        opacity: .8;
      }
    }
}

</style>