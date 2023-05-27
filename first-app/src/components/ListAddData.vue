<template>
    
    <div class="ListAddData">
        <div class="addList">

            <FormAddData v-on:submit-item="submit" v-bind:edit-index="editIndex" v-bind:name="name" v-on:edit-item="edit"/>
            <ul>
                <li v-for="(item,index) in items" v-bind:key="index">
                    <span>{{ item }}</span>
                    <div class="editDeletelist">
                        <i class="fa-solid fa-pen-to-square" v-on:click.prevent="editItem(index)"></i>
                        <i class="fa-solid fa-trash" v-on:click.prevent="deleteItem(index)"></i>
                    </div>
                </li>
            </ul>
        </div>

    </div>

</template>

<script>
import FormAddData from './FormAddData.vue'

export default {
    name:'ListAddData',
    components:{
        FormAddData,
    },
    data() {
      return{
        items:[],
        name:"",
        editIndex:-1,
      }  
    },
    methods:{
        submit:function(name){
            this.items.push(name);
            this.name="";
        },
        edit:function(obj){
            var {name, editIndex}=obj;
            console.log("actual edit",name,editIndex);
            this.items.splice(editIndex,1,name);
            this.name="";
            this.editIndex= -1;
        },
        editItem:function(index){
            console.log("edit index");
            this.editIndex=index;
            this.name=this.items[index];
        },
        deleteItem:function(index){
            this.items.splice(index,1);
        },
    }
}
</script>

<style scoped>
    .addList li{
        border: 1px solid #000;
        padding: 5px;
        list-style-type: none;
    }
    .editDeletelist{
        float:right
    }
    .editDeletelist i{
        margin-right: 15px;
    }

</style>
