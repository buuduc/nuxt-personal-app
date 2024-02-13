<template>
    <div class="big">
        <div class="box">
            <div>
                <span v-for="i in 5" key="i"></span>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
definePageMeta({ layout: false })
</script>

<style scoped>
.big {
    margin: 0;
    padding: 0;
    background: #607d8b !important;
    width: 100vw;
    height: 100vh;
}
.box{
    position: absolute;
    top: calc(50% - 150px);
    left: calc(50% - 100px);
    transform: perspective(1000px) rotateY(-45deg);
    /* perspective: 1000px; */
    transform: rotateY(-45deg);
    display: block ;
    width: 200px;
    height: 300px;
    transform-style: preserve-3d;
    background: none;
    &::before{
        content: "";
        position: absolute;
        bottom: -100px;
        left: 0;
        width: 100%;
        height: 50px;
        background-color: #000;
        filter: blur(40px);
        opacity: 0.5;
        
        transform: rotateX(50deg);
    }
    /* background-color: red; */
    div{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        transform-style: preserve-3d;
        animation: animate 5s linear infinite;

        span{
            position: absolute;
            top: 0;
            left: 0;
            display: block;
            width: 100%;
            height: 100%;
            background: linear-gradient(0deg, #f1f1f1, #bbb, #f1f1f1);
            border-radius: 20px;
            &:nth-child(2){ transform: rotateX(45deg); }
            &:nth-child(1){ transform: rotateX(0deg); }
            &:nth-child(3){ transform: rotateX(-45deg); }
            &:nth-child(4){ transform: rotateX(90deg); }
        }
    }
    @keyframes animate {
        0%{
            transform: perspective(1000px) rotateX(0deg);
        }
        100%{
            transform: perspective(1000px) rotateX(-359deg);
        }
    }
}
</style>
