<template>
    
    <div class="control">

        <button v-on:click="control">{{ title}}</button>

    </div>

</template>

<script>

export default {
    name:`Control`,
    props:['control','title'],
    data() {
        
    },
}
</script>

<style scoped>

</style>