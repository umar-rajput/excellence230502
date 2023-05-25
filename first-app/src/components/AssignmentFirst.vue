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
    </div>

</template>

<script>

export default {
    name:'AssignmentFirst',
    data() {
        return{
            fname:"",
            lname:"",
            address:"",
            items:[],
            isRed:false,
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
</style>