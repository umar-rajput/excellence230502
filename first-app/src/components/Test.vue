<template>
    <div class="testing">
        <p>{{ msg }}</p>
        <p>{{ write }} Testing</p>
        <input v-model="write" placeholder="Write something">
        <button @click="clearInput" class="clearButton">Clear</button> 
        <br>
        <button @click="capitalLetter" class="upperCaseButton">Make Input Capital</button>
    </div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'

export default {
    name:`Test`,
    data:()=> {
        return{
            msg:"Hello RAJPUT",
            write:''
        }
    },
    methods:{
        clearInput(){
            this.write='';
        },
        capitalLetter(){
            this.write=this.write.toUpperCase();
        }
    }
}
</script>

<style>
    .clearButton{
        margin-left: 5px;
    }
    .upperCaseButton{
        margin-top: 8px;
        padding: 0px 54px;
    }
</style>