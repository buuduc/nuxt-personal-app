<template>
    <section>
        <h2>Yeu Truc Phuong</h2>
        <div class="banner">
            <div v-for="i in 220" :key="i" class="blocks" :style="calculateStyle(i)"></div>
        </div>
    </section>
</template>

<script setup >
    definePageMeta({
    layout: false
    })
    const calculateStyle = (i) => {
        const index = i - 1 
        const x = (i-1)*5
        const delay = (i-1) * 0.05
        const y = (index- (index%20))/20*5
        return `animation-delay: ${delay}s; background-position: -${x}vw -${y}vw;`
    }
</script>

<style lang="scss" scoped>
*{
    margin: 0;
    padding: 0;
    // font-family: 'Poppins', sans-serif;
    background: #333;
}
h2 {
    z-index: 999999;
    background: none;
    // position: relative;
}
section{
    position: relative;
    width: 100%;
    height: 100vh;
    text-align: center;
    line-height: 100vh;
    font-size: 5vw;
    color: #fff;
    font-weight: 700;
    .banner{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        display: flex;
        flex-wrap: wrap;
        background: none;
        // background: url('/background.jpeg');


        .blocks{
            opacity: 0;
            position: relative;
            display: block;
            width: 5vw;
            height: 5vw;
            background: url('/assets/background.jpeg');

            animation: test-animation 0.75s ease-in-out forwards;
            &:nth-child(even){
                animation-duration: 1s;
            };
            &:nth-child(7n+3){
                animation-duration: 1s;
            };
            &:nth-child(7n+7){
                animation-duration: 1s;
            };
        }
    }
}
@keyframes test-animation {
    0%{
        opacity: 0;
        transform: scale(0) translateY(1000px);
        
    }
    50%{
        opacity: 1;
        // border-radius: 50%;
        // background-position: center;
        // background-attachment: fixed;
    }
    99%{
        //  border-radius: 50%;
    }
    100%{
        opacity: 1;
        transform: scale(1) translateY(0px);
        // background-position: center;
        // background-attachment: fixed;
    }
}
</style>
