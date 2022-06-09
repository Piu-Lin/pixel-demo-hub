<template>
<div id="bottomBox">
  <div @click="switchDayNight" class="Mode">
    <img class="bottonBg" src="/src/assets/Interaction/bottom1.png"/>
    <img class="Icon" src="/src/assets/Interaction/night.png" alt=""/>
    <div class="modeContent">夜间模式</div>
  </div>
  <!-- <div @click="snedAssignMessage(night)" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/night.svg" alt=""/>
    <div class="modeContent">夜间</div>
  </div>
  <div @click="snedAssignMessage(res)" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/initLoaction.svg" alt=""/>
    <div class="modeContent">重置</div>
  </div>
  <div @click="snedAssignMessage(play)" class="Mode">
      <img class="Icon" src="/src/assets/Interaction/play.svg" alt=""/>
      <div class="modeContent">播放</div>
  </div>
  <div @click="snedAssignMessage(sunny)" class="Mode">
      <img class="Icon" src="/src/assets/Interaction/play.svg" alt=""/>
      <div class="modeContent">晴天</div>
  </div>
  <div @click="snedAssignMessage(rainy)" class="Mode">
      <img class="Icon" src="/src/assets/Interaction/play.svg" alt=""/>
      <div class="modeContent">雨天</div>
  </div> -->
</div>
  

</template>

<script setup>
import {ref} from 'vue'
const day='{"eventname": "Event_day"}'
const night='{"eventname": "Event_night"}'
let isNight = ref(false)
const switchDayNight=()=>{
  isNight?snedAssignMessage(day):snedAssignMessage(night)
  isNight=!isNight
}

const res='{"eventname": "Event_reset_default_view"}'
const play='{"eventname": "Event_play_movie"}'
const sunny='{"eventname": "Event_sunny_day"}'
const rainy='{"eventname": "Event_rainny_day"}'



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
    bottom:20px;
    width:100%;
    justify-content:center;
    z-index: 2;
    .Mode{
      display: flex;
      position: relative;
      margin: 0px 10px;
      align-items: center;
      cursor: pointer;
      .Icon{
        width: 30px;
        height: 30px;
      }
      .bottonBg{
        position: absolute;
        width: 150%;
        height: 150%;
      }
      .modeContent{
        font-size:24px;
        color: black;
        opacity:.7;
      }
    }
    

}

</style>