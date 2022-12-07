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
  methods:{
        //promiss 
          async fetchMotels(){
          const res = await fetch ("https://motel-system.herokuapp.com/api")
          const data = await res.json()
          console.log(data)
          return data.motels
        }
      },
      async created(){
        this.motels = await this.fetchMotels()
      }
  /**
  mounted(){
    //fetch("https://motel-management-system.herokuapp.com/api")
     fetch("http://localhost:4167/api")
      .then(res => res.json())
      .then(data => this.motels = data)
      .catch(err => console.log(err.message))
  }
  */
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
