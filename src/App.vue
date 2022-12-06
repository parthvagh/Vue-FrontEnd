<template>
  <div class="container">
    <HeaderTop projectName="Motel Management System" devName="By Parth Vaghasiya" />

    <MotelBox :motels="motels" />

  </div>
</template>

<script>

import HeaderTop from './components/HeaderTop.vue'
import MotelBox from './components/MotelBox.vue'

export default {
  name: 'App',
  components: {    
    HeaderTop,
    MotelBox
  },

  data(){
    return {
      motels: []
    }

  },
  mounted(){
    
    fetch("http://localhost:4167/api", {method:"POST"},)
      .then(res => res.json())
      .then(data => this.motels = data)
      .catch(err => console.log(err.message))
  }
}

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  background-color: rgba(90, 118, 135, 0.101);
  max-width: 100%;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}

</style>
