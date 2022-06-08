<template>
<div id="bottomIcon">
  <div @click="snedAssignMessage(day)" class="Mode">
    <img class="Icon" src="/src/assets/Interaction/day.svg" alt=""/>
    <div class="modeContent">日间</div>
  </div>
  <div @click="snedAssignMessage(night)" class="Mode">
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
  </div>
</div>
  

</template>

<script setup>

const day='{"eventname": "Event_day"}'
const night='{"eventname": "Event_night"}'
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
#bottomIcon{
    display: flex;
    position:absolute; 
    bottom:20px;
    width:100%;
    justify-content:center;
    z-index: 2;
    .Mode{
      display: flex;
      margin: 0px 10px;
      background-color:white;
      opacity:.7;
      align-items: center;
      border: 2px solid white;
      border-radius: 8px;
      cursor: pointer;
      .Icon{
        width: 30px;
        height: 30px;
      }
      .modeContent{
        font-size:24px;
        color: black;
        opacity:.7;
      }
    }
    

}

</style>