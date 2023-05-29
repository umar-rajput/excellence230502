<template>
    
    <div class="AssignmentFirst">
        <h2>Assignment - 1</h2>
        <h3>Customer Details</h3>
        <form v-on:click.prevent>
            <label for="fname">First Name</label>
            <input type="text" placeholder="Enter First Name" v-model="fname" class="inputfield">
            <label for="lname">Last Name</label>
            <input type="text" placeholder="Enter Last Name" v-model="lname" class="inputfield">
            <label for="address">Address</label>
            <input type="text" placeholder="Enter Address" v-model="address" class="inputfield">
            <button v-on:click="submit" type="button">Add</button>
        </form>
        <table>
            <tr>
                <th>First Name</th>
                <th>Last Name</th>
                <th>Address</th>
                <th>Checkbox</th>
                <th>Delete</th>
            </tr>
            <tr v-for="(item,index) in items" v-bind:key="index">
                <td :class="{red:isRed}">{{ item.fname }}</td>
                <td :class="{red:isRed}">{{ item.lname }}</td>
                <td :class="{red:isRed}">{{ item.address }}</td>
                <td>
                    <input type="checkbox" v-on:click="isRed=!isRed">
                </td>
                <td>
                    <i class="fa-solid fa-trash" v-on:click.prevent="deleteItem(index)"></i>
                </td>
                <!-- <td v-for="(item,index) in items" v-bind:key="index">{{ item }}</td>
                <td v-for="(item,index) in items" v-bind:key="index">{{ item }}</td> -->
            </tr>
        </table>
        <!-- <ul>
            <li v-for="(item,index) in fname" v-bind:key="index">{{ fname }}</li>
            <li v-for="(item,index) in items" v-bind:key="index">{{ items[0] }}</li>
        </ul> -->
        
        <!-- create a button component and call 2 times and perform differnt task on both -->
        <div class="buttons">
            <BaseButton title="Open alert" :alert="alertMsg"/>
            <div class="reverseMsg">
                <input type="text" v-model="msg" placeholder="Write Something.." class="inputField">
                <BaseButton title="Reverse" :alert="reverseMsg"/>
                <!-- <BaseButton v-for="post in posts" :key="post.id" :title="posts.title"/> -->
            </div>
        </div>
    </div>

</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
    name:'AssignmentFirst',
    components:{
        BaseButton
    },
    data() {
        return{
            fname:"",
            lname:"",
            address:"",
            items:[],
            isRed:false,
            msg:"",
        }
    },
    methods:{
        submit: function(){
            // console.log(this.fname,this.lname,this.address);
            this.items.push({'fname':this.fname,
                             'lname':this.lname, 
                             'address':this.address});
            this.fname="";
            this.lname="";
            this.address="";    
        },
        deleteItem: function(index){
            this.items.splice(index,1);
        },
        alertMsg: function(){
            alert('alert msg');
        },
        reverseMsg: function(){
            this.msg=this.msg.split("").reverse().join("");
        }

    },
    
}
</script>

<style scoped>

    .inputfield{
        margin: 0px 10px;
    }

    table{
        width: 85%;
        margin: 15px 65px;
        padding: 6px;
    }
    table,tr,td,th{
        border: 1px solid #000;
        border-collapse: collapse;
    }
    .red{
        color:red;
    }

    .baseButton::v-deep .primaryButton{
        background-color:#5A6268;
        padding: 10px ;
        border-radius: 10px;
    }
    .reverseMsg{
        margin: 17px 0px;
        display: flex;
        justify-content: center;
        gap: 10px;
    }
    .inputField{
        border-radius: 5px;
    }
</style>