<template>
    
    <div class="FormAddData">
        <p>Enter the data and hit enter</p>
        <form v-on:submit.prevent>
            <input type="text" v-on:keypress="submit" v-model="text">
        </form>

    </div>

</template>

<script>

export default {
    name:'FormAddData',
    data() {
        return{
            text:"",
            
        }
    },
    watch:{
        name:function(newName){
            console.log("watch  ",newName);
            this.text=newName;
        }
    },
    props:{
        name:{type:String, require:true},
        editIndex:{type:Number, require:true},
    },
    methods:{
        submit:function(e){
            console.log(this.editIndex);
            console.log(this.text);
            if(e.keyCode===13){
                if(this.editIndex!== -1){
                    console.log("edit item");
                    this.$emit("edit-item",{
                        name:this.text,
                        editIndex:this.editIndex
                    });
                }else{
                    this.$emit("submit-item",this.text);
                }
                this.text="";
            }
        }
    },
}

</script>

<style scoped>

</style>