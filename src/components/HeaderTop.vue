<template>
    <div>
        <h1> {{projectName}} </h1><br>
        <h4> {{devName}} </h4><br>
    </div>
</template>
    
<script>
    export default{
        name: 'HeaderTop',
        props:{
            projectName: String,
            devName:String
        }
    }
</script>
    
<style scoped>
    div{
        text-align: center;
    }
</style>