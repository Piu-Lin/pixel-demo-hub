<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Connect from './connect.vue'
import MessageDemo from './components/messageDemo.vue'
import Home from './pages/Home.vue';

</script>

<template>
<MessageDemo/>
<Connect/>
</template>

<style>
body {
    width : 100vw;
    height : 100vh;
    margin: 0;
}
</style>
