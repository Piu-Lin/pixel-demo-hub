<template>
   <div class="nav-card">
        <div class="book-mark">
            {{contentText.cornerMark}}
        </div>
        <div class="card-word">
            {{contentText.title}}
        </div>
    </div>
</template>

<script setup>
const props=defineProps({
    contentText:Object
})
const {contentText} = props

</script>

<style scoped>
.nav-card{
    position: relative;
    height: 100%;
    width: 140%;
    background-color: black;
    opacity: 0.3;
    border-radius: 10px 10px 0px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.book-mark{
    position: absolute;
    width: 18%;
    height: 18%;
    left: 10%;
    top: 0%;
    background-image: linear-gradient(to bottom, red,transparent);
    text-align: center;
    padding-top: 5%;
    color:blanchedalmond ;
}
.wi{
    background-image: linear-gradient(to bottom, blanchedalmond,transparent);
}
.card-word{
    width: 40%;
    font-size: 150%;
    color: white;
    margin-bottom: 70%;
}
</style>