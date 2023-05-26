<template>
    
    <div class="FormAddData">
        <p>Enter the data and hit enter</p>
        <form v-on:submit.prevent>
            <input type="text" v-on:keypress="submit" v-model="name">
        </form>

    </div>

</template>

<script>

export default {
    name:'FormAddData',
    data() {
        return{
            name:"",
            
        }
    },
    methods:{
        submit:function(e){
            if(e.keyCode===13){
                this.$emit("submit-item",this.name);
                this.name="";
            }
        }
    },
}

</script>

<style scoped>

</style>