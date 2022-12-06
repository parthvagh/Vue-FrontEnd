<template>
    <div :class="motel.isAnyRoomAvailable ? 'green': 'red' ">
        
        <h2> <i> {{motel.name}} </i> </h2><br>
        <h4> Address: {{motel.address}} </h4>
        <h4> Phone: {{motel.phone}} </h4>
        <h4> Total Rooms: {{motel.total_rooms}} </h4>
        <h4> Average Cost: {{motel.average_cost}} </h4>
        <h4> Rating: {{motel.rating}}/5 </h4>
    </div>

</template>

<script>


export default{
    name: 'MotelItem',
    props:{
        motel: Array
    }
}


</script>

<style scoped>


h4{
    margin: 2px;
}

div{
    background-color: rgb(106, 168, 110);
    color: black;
    padding: 1em;
}

.red{
background-color: rgb(98, 77, 141) !important;

}
.green{
    color: white;
}


</style>