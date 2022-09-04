<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button type="button" @click="getData('Function Called')">SingleClick Button</button>
    <button type="button" @dblclick="getData('Function Called')">Double Click Button</button>
    <h2 @mousemove="getConsole()" >Detected Mouse move event</h2>
    <h2>{{changeValue}}</h2>
    <button @click="getIncrementValue">Increment Value</button>
    <button @click="getDicrementValue">Dicrement Value</button>
    <h2>Get Input fields value</h2>
    <input type="text" placeholder="Enter email" v-model="email">
    <br>
    <br>
    <input type="password" placeholder="Enter Password" v-model="pass">
    <br><br>
    <button type="button" @click="getDataValue">Get Data</button>
    
  </div>
</template>

<script>

export default {
  name: "aboutPage",
  data() {
    return {
      changeValue: 0,
      email:null,
      pass:null
    }
  },
  methods: {
    getDataValue(){
      console.warn("Values :", this.email, this.pass)
    },

    getData(x) {
      alert(x);
    },
    getConsole(){
      console.log("mouse is moving")
    },
    getIncrementValue(){
        return this.changeValue++
    },
    getDicrementValue(){
      return this.changeValue--
    }

  },
};
</script>
