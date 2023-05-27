<template>
    
    <div class="timer">
        <div class="timer-main">
            <h1>Timer</h1>
            <h2>{{ hr }} : {{ min }} : {{ sc }} : {{ mils }}</h2>
            <div class="buttons">
                <control title="Start" :control="start" class="startButton"/>
                <control title="Stop" :control="stop" class="stopButton"/>
            </div>
        </div>
    </div>

</template>

<script>
import Control from './Control.vue'


export default{
    name:`Timer`,
    components: { Control },
    data() {
        return{
            timer:0,
            timerId:false,
            hr:0,
            min:0,
            sc:0,
            mils:0,

        }

    },
    methods:{
        alertmsg:function(){
            alert("Button call");
        },
        start:function(){
            this.timerId=setInterval(()=>{
                this.mils++;
                if(this.mils==100){
                    this.sc++;
                    this.mils=0;
                }
                if(this.sc==60){
                    this.min++;
                    this.sc=0;
                }
                if(this.min==60){
                    this.hr++;
                    this.min=0;
                }
            },10);
        },
        stop:function(){
            clearInterval(this.timerId);
        }
    },
}
</script>

<style scoped>
    .timer{
        display: flex;
        justify-content: center;
        margin: 30px 0px;
    }
    .timer-main{
        height: 270px;
        width: 270px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border: 15px solid #35495e;
        background: #41b883;
        border-radius: 50%;
    }
    .buttons{
        display: flex;
        justify-content: center;
        gap: 10px;
    }
    .control::v-deep button{
        padding: 10px 20px;
        font-weight: bold;
        background: #2c3e50;
        border-radius: 10px;
    }

    .startButton::v-deep button{
        color: #41b883;
    }
    .stopButton::v-deep button{
        color: #bd2626;
    }

</style>