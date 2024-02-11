<template>
    <div>
        <section>
            <div class="loader">
            <span v-for="i in 20" :style="`--i:${i};`"></span>
        </div>
        </section>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
section{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #333;
}

.loader{
    position: relative;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    /* background: linear-gradient(#2196f3, #21cbf3); */
    display: flex;
    justify-content: center;
    align-items: center;
    /* animation: animateBg 10s linear infinite; */
    span{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 100%;
        transform: rotate(calc(18deg * var(--i)));
        &::before{
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 15px;
            height: 15px;
            background-color: #00ff0a;
            box-shadow: 0 0 10px #00ff0a,
                        0 0 20px #00ff0a,
                        0 0 40px #00ff0a,
                        0 0 60px #00ff0a,
                        0 0 80px #00ff0a; 
            border-radius: 50%;
            animation: animate 2s linear infinite;
            animation-delay: calc(0.1s * var(--i));
        }
    }
}
@keyframes animateBg {
    0%{
        filter: hue-rotate(0deg);
    }
    100%{
        filter: hue-rotate(360deg);
    }
    
}

@keyframes animate {
    0%{
        transform: scale(1);
    }
    80%,100%{
        transform: scale(0);
    }
}

</style>
