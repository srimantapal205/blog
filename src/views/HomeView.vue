<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h2>{{email}}</h2>
    <P>{{getName('Javascript')}}</P>
    <p>{{getData()}}</p>
    <p>{{getData().name}}</p>
    <p>{{getData().email}}</p>
  </div>
  <h2> two way binding</h2>
  <input type="text" name="incValue" id="inc" v-model="count">
  <h3>{{count}}</h3>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data() {
    return {
      email: "test@test.com",
      count:110
    }
  },
  methods: {
    getName(x) {
      return x
    },
    getData(){
      return {
        name:"This is return Object",
        email:"return@test.in", 
        email2:this.email
      }
    }
  },
}
</script>
