<script setup>

import Connect from './connect.vue'
import MessageDemo from './components/messageDemo.vue'
import Home from './pages/Home.vue'
import { useStore } from 'vuex'
import { computed } from 'vue'
const store  = useStore()
const count = computed(() => store.getters.count)
</script>

<template>
<MessageDemo/>
<!-- <Connect/> -->
</template>

<style>
body {
    width : 100vw;
    height : 100vh;
    margin: 0;
}
</style>

