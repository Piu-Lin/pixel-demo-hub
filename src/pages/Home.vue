<template>
  <TopInformation/>
  <div class="home-content">
    <div v-for="contentText,index in navList" :key="index">
      <Navcard :contentText="contentText"></Navcard>
      
    </div>

  </div>
</template>

<script setup>
import TopInformation from '../components/topInformation.vue'
import Navcard from './components/Navcard.vue';
const navList=[
    {"cornerMark":"忆","title":"湾区溯源","image":""},
    {"cornerMark":"变","title":"蝶变重生","image":""},
    {"cornerMark":"玩","title":"活力古城","image":""},
    {"cornerMark":"览","title":"博物馆群","image":""},
    ]
</script>

<style scoped>
.home-content{
    position:  absolute;
    z-index: 1;
    width: 70%;
    height: 80%;
    left: 50%;
    bottom: 0px;
    display: flex;
    justify-content: space-between;
    color:white;
    transform: translate(-50%);
}
</style>