<template>
    <div class="testing">
        <p>{{ msg }}</p>
        <p>{{ write }} Testing</p>
        <input v-model="write" placeholder="Write something">
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
}
</script>
