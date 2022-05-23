<template>
  <div class="top-information">
    <div class="title">旅游导览</div>
    <div class="infomation-content">
        <div>10:46</div>
        <div>|</div>
        <div>2022.05.12</div>
        <div>|</div>
        <div>阴</div>
        <div>|</div>
        <div>19°C</div>
    </div>
</div>
</template>

<script setup>

</script>

<style scoped>
.top-information{
    position: absolute;
    width: 100%;
    z-index: 1;
    display: flex;
    justify-content:space-between;
}
.title{
    font-size: 1rem;
    font-weight: 600;
    color: blanchedalmond;
    margin-left: 2.5rem;
}   
.infomation-content{
    display: flex;
    font-size: 1rem;
    margin-right: 2.5rem;
    color: blanchedalmond;
}
</style>