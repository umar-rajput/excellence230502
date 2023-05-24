<template>
    <div class="testing">
        <p>{{ msg }}</p>
        <span :class="{red:isRed}">{{ write }} Testing</span> 
        <input type="checkbox" @click="isRed=!isRed">
        <p>{{ gettime }}</p>
        <input v-model="write" placeholder="Write something">
        <button @click="clearInput" class="clearButton">Clear</button> 
        <br>
        <button @click="capitalLetter" class="upperCaseButton">Make Input Capital</button>
        <br>
        <div class="dropdown">
            <span v-bind:style="{color:colorValue.color}" >Select color from dropdown</span>
            <select v-model="colorValue" id="">
                <option v-bind:value="{color:'red'}">Red</option>
                <option v-bind:value="{color:'blue'}">Blue</option>
                <option v-bind:value="{color:'yellow'}">Yellow</option>
                <option v-bind:value="{color:'black'}">Black</option>
            </select>
        </div>
        
    </div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'

export default {
    name:`Test`,
    data:()=> {
        return{
            msg:"Hello RAJPUT",
            write:'',
            gettime:false,
            isRed:false,
            colorValue:{
                color:'red'
            },
        }
    },
    // created: function(){
    //     console.log("created");
    //     // this.gettime=new Date();  //if show date and time 
    //     this.gettime=new Date().getFullYear()+"-"+new Date().getMonth()+"-"+new Date().getDate();
    // },
    // mounted: function(){
    //     console.log("mounted");
    //     // this.gettime=new Date();
    //     this.gettime=new Date().getFullYear()+"-"+new Date().getMonth()+"-"+new Date().getDate();
    // },
    // updated: function(){
    //     console.log("updated");
    //     // this.gettime=new Date();
    // },
    // unmounted: function(){
    //     console.log("destroyed");
    //     this.gettime=new Date();    
    // },
    methods:{
        clearInput(){
            this.write='';
        },
        capitalLetter(){
            this.write=this.write.toUpperCase();
        },
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
    .red{
        color:red;
    }
    .dropdown{
        margin-top: 10px;
    }
    .dropdown>span{
        margin-right: 5px;
    }
</style>