<template>
    <div class="motelbox">
        
        <div v-for="motel in motels" :key="motel.id" >
            <MotelItem :motel="motel"/>
        </div>

    </div>
    


</template>

<script>

    import MotelItem from './MotelItem.vue'


    export default{
        name: 'MotelBox',
        components: {
            MotelItem
        },
        props:{
            
            motels: Array
        }
    }

</script>

<style scoped>

.motelbox{


padding: 1em;
color: gray;
}

</style>