<template>
    <div class="big-container">
        <div class="cube-container">
            <input type="text" value="Hiteme">
            <div class="box">
                <div class="card" id="front">Front</div>
                <div class="card" id="back">Back</div>
                <div class="card" id="left">Left</div>
                <div class="card" id="right">Right</div>
                <div class="card" id="bottom">Bottom</div>
                <div class="card" id="top">Top</div>
            </div>
    
        </div>
    </div>
</template>

<script setup lang="ts">
    definePageMeta({ layout: false })
</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
}
.big-container{
    height: 100vh;
    background: radial-gradient(rgb(5,221,245), rgb(6,150,253));
}
.cube-container{
    height: 60vh;
    width: 30vw;
    position: absolute;
    top: 50vh;
    left: 50vw;
    transform: translate(-50%, -50%);
    perspective: 1000px;
    .box{
        height: 250px;
        width: 250px;
        position: absolute;
        top: 100px;
        left: 100px;
        transform-style: preserve-3d;
        /* transform: rotateY(30deg); */
        animation: animate 5s infinite;
        .card{
            height: 250px;
            width: 250px;
            text-align: center;
            padding: 100px 0px;
            color: white;
            background-color: black;
            border: 2px solid white;
            font-size: 32px;
            box-sizing: border-box;
            position: absolute;
            transition: all 1s;
        }
    }
    #front{
        transform: translateZ(125px);
    }
    #back{
        transform: translateZ(-125px);
    }
    #left{
        right: 125px;
        transform: rotateY(-90deg);

    }
    #right{
        left: 125px;
        transform: rotateY(90deg);

    }
    #top{
        bottom: 125px;
        transform: rotateX(90deg);

    }
    #bottom{
        top: 125px;
        transform: rotateX(-90deg);

    }
    @keyframes animate {
        0%{ transform: rotateX(45deg) rotateY(-45deg); }
        25%{ transform: rotateX(-45deg) rotateY(-45deg); }
        50%{ transform: rotateX(45deg) rotateY(45deg); }
        75%{ transform: rotateX(-45deg) rotateY(45deg); }
        100%{ transform: rotateX(45deg) rotateY(-45deg); }
    }
}
/* input:focus~ .box #front{ color: red; transform: translateZ(180px) rotateY(360deg); } */
input:focus ~ {
    &.box {
        &.box #front{ transform: translateZ(180px) rotateY(360deg); }
        #back{ transform: translateZ(-180px) rotateY(360deg); }
        #left{ right:180px }
        #right{ left:180px }
        #top{ bottom:180px }
        #bottom{ top:180px }
    }
}
/* input:focus~{
    color: red;
    &.box{
        #front{
            transform: translateZ(180px) rotateY(360deg);
        }
    }
} */
</style>
