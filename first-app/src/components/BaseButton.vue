<template>
    
    <div class="baseButton">

        <button class="primaryButton" @click="alert">
            {{title}}
        </button>

    </div>

</template>

<script>

export default {
    props:['title','alert'],
    // data() {
    //     return{
            
    //     }
    // },
    // methods:{
        
    // }
}
</script>


<style scoped>
    .primaryButton{
        background-color: #0069D9;
        color:#fff;
    }

</style>